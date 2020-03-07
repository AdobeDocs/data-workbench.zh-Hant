---
description: DWB中不同檔案傳輸方法的快速指南。
title: 檔案傳輸管理
uuid: a3e19f8a-1cc4-437c-9661-408f675109c0
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 檔案傳輸管理{#file-transfer-governance}

DWB中不同檔案傳輸方法的快速指南。

檔案傳輸控制是將檔案從內部目錄傳輸到任何其他伺服器或內部檔案移動的標準過程。

## 不同的檔案傳輸方法 {#section-972bb39ba1954c6ebd35f6d042593efe}

1. AWS(Amazon Web Services)

   1. 如果尚未安裝，請提交票證以在伺服器上安裝AWS命令行介面(請參 [見http://docs.aws.amazon.com/cli/latest/userguide/installing.html](http://docs.aws.amazon.com/cli/latest/userguide/installing.html))。
   1. 如何檢查？ 嘗試使用命令提示符配置AWS(請參 [見http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html](http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html))。

1. 將檔案從FTP伺服器傳輸到NAS目錄。

   1. 從FTP伺服器到NAS目錄的FTP離線饋送。 FTP需要下列詳細資訊。

      ftp_username

      ftp_password

      ftp_port

      ftp_address

      ftp_directory

      delete_ftp_files

      ftp_file_extension

      local_directory

      (專案檢查清單中將提供「FTP詳細資料」。 使用外部ftp使用者來傳輸檔案)

   1. 使用下方附加的ftp_winscp_get.pl指令碼，並根據需求進行排程。

      ftp_winscp_get.pl

      此指令碼應放在E:\scripts\Scripository\Library\Perl

      >[!NOTE]
      >
      >如果「Scriptository」檔案夾不可用，請參 [閱「每週重新處理](../../../home/dwb-implement-overview/dwb-implement-configure/dwb-implement-reprocess-scripting.md#concept-60529e12d6d94386a02c1c6fdedf0295) 」以下載檔案夾。

   1. 根據ftp_address上的檔案可用性來排程指令碼。
   1. 檔案的命名慣例應為YYYYMMDD-&lt;offline_feed_name>-00。*

1. 將檔案從NAS目錄傳輸到FTP伺服器。

   1. 根據需求使用ftp_winscp_put.pl指令碼和排程。

      此指令碼應放在E:\scripts\Scripository\Library\Perl

      以下詳細資訊是執行指令碼所必需的。

      ftp_username

      ftp_password

      ftp_port

      ftp_address

      ftp_directory

      delete_ftp_files

      ftp_file_extension

      local_directory

      ```
      ####################################################################################################################### 
      # PLUGIN NAME HERE 
      my $pluginname = "FTP WinSCP"; 
      # 20140421 Script tp put files on the FTP 
      ####################################################################################################################### 
      # INCLUDE SCRIPOSITORY CORE 
      use FindBin;                 # locate this script 
      BEGIN {push @INC, $FindBin::Bin} 
      require 'core.pl'; 
      
         # check for the required parameters 
       GetOptions('local_directory:s'     => \$local_directory, 
                     'source_file_pattern:s' => \$source_file_pattern, 
                     'ftp_file_extension:s' => \$ftp_file_extension, 
                     'ftp_address=s'  => \$ftp_address, 
                     'ftp_username=s'  => \$ftp_username, 
                     'ftp_password:s'  => \$ftp_password, 
                     'ftp_port:s'   => \$ftp_port, 
                     'ftp_directory:s'     => \$ftp_directory, 
           'log_directory:s'  => \$log_directory, 
                     'error_directory:s'  => \$error_directory, 
                     'mail_from:s'  => \$mail_from, 
                     'mail_to:s'   => \$mail_to, 
                     'host:s'   => \$host, 
                     'trigger_directory:s' => \$trigger_directory, 
                     'trigger_file_extension:s' => \$trigger_file_extension, 
                     'delete_ftp_files:s'  => \$delete_ftp_files,); 
      
       # FOR LEFT OVER PARAMS, WE CAN CHECK GLOBAL PARAMS 
       check_parameters(@argv); 
      
       my $ftp_winscp_script = "winscpscript.txt"; 
       if (index($trigger_file_extension, '.') != -1) { 
        my @trigger_file_extension1=split(/\./,$trigger_file_extension,2); 
        $trigger_file_extension =  $trigger_file_extension1[1]; 
       } 
       if (index($ftp_file_extension, '.') != -1) { 
        my @ftp_file_extension1=split(/\./,$ftp_file_extension,2); 
        $ftp_file_extension =  $ftp_file_extension1[1]; 
       } 
       if ($trigger_file_extension ne "_empty_" && $trigger_directory ne "_empty_") { 
         print $trigger_file_extension; 
        my $ftp_winscp_trigger_script = "winscpscript_trigger.txt"; 
        create_winscp_script($ftp_winscp_trigger_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$trigger_directory,$ftp_directory,$delete_ftp_files,"*",$trigger_file_extension); 
        sleep(10); 
        system("\"E:\\Scripts\\Scripository\\Library\\WinSCP\\WinSCP.exe\" /console /script=$ftp_winscp_trigger_script /log=$logfile"); 
        $files = getFiles($trigger_directory,$trigger_file_extension,$days_ago,$months_ago); 
        my $ftp_file_pattern=""; 
        my $numberoffiles = @$files; 
        my $i=0; 
        foreach my $trigger_file(@$files) { 
         $i++; 
         my $file_string=substr($trigger_file,length($trigger_directory), length($trigger_file)-length($trigger_directory)); 
         my @file_string1=split(/\./, $file_string, 2); 
         if ($i == $numberoffiles) { 
          $ftp_file_pattern.=$file_string1[0].".".$ftp_file_extension; 
         } 
         else { 
          $ftp_file_pattern.=$file_string1[0].".".$ftp_file_extension.", "; 
         }
      
        } 
      
        #unlink($ftp_winscp_trigger_script); 
        print $local_directory; 
        print $trigger_directory; 
        create_winscp_script($ftp_winscp_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$local_directory,$ftp_directory,$delete_ftp_files,$ftp_file_pattern, ""); 
        runLogger("$pluginname: Sleeping for 10 sec to give enough time for the temp script to be available"); 
        sleep(10); 
        runLogger("$pluginname: FTP started"); 
        system("\"E:\\Scripts\\Scripository\\Library\\WinSCP\\WinSCP.exe\" /console /script=$ftp_winscp_script /log=$logfile"); 
        runLogger("$pluginname: FTP ended"); 
      
       } 
       else { 
        if ($source_file_pattern eq "_empty_") { 
         $source_file_pattern="*"; 
        } 
        else { 
         if (index($source_file_pattern, '.') != -1) { 
          my @source_file=split(/\./,$source_file_pattern,2); 
          $source_file_pattern =  $source_file[0]; 
         } 
        } 
        $ftp_file_extension=".".$ftp_file_extension; 
      print $local_directory; 
        create_winscp_script($ftp_winscp_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$local_directory,$ftp_directory,$delete_ftp_files,$source_file_pattern,$ftp_file_extension); 
        runLogger("$pluginname: Sleeping for 10 sec to give enough time for the temp script to be available"); 
        sleep(10); 
        runLogger("$pluginname: FTP started"); 
        system("\"E:\\Scripts\\Scripository\\Library\\WinSCP\\WinSCP.exe\" /console /script=$ftp_winscp_script /log=$logfile"); 
        runLogger("$pluginname: FTP ended"); 
       } 
       unlink($ftp_winscp_script);
      
      sub create_winscp_script() { 
       my ($ftp_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$local_directory,$ftp_directory,$delete_ftp_files,$file_pattern, $file_extension) = @_; 
       open (FTP, "> $ftp_script") or die "Can't open log: $!"; 
       print FTP "\# Automatically answer all prompts negatively not to stall\n"; 
       print FTP "option batch on\n\n"; 
       print FTP "\# Disable overwrite confirmations that conflict with the previous\n"; 
       print FTP "option confirm off\n\n"; 
       print FTP "\# Connect using a password\n"; 
       if ($ftp_port eq "22") { 
        print FTP "open sftp://$ftp_username:$ftp_password\@$ftp_address\n\n"; 
       } 
       else { 
        print FTP "open ftp://$ftp_username:$ftp_password\@$ftp_address\n\n"; 
       } 
       print FTP "\# Change local directory\n"; 
       print FTP "lcd \"$local_directory\"\n\n"; 
       print FTP "\# Change remote directory\n"; 
       if ($ftp_directory eq "_empty_") { 
       } 
       else { 
        print FTP "cd \"$ftp_directory\"\n\n"; 
       } 
       print FTP "\# Force binary mode transfer\n"; 
       print FTP "option transfer binary\n\n"; 
       print FTP "\# Download the file to specified directory\n"; 
       my @get_files=split(/,/,$file_pattern); 
       foreach my $file (@get_files){ 
        if ($delete_ftp_files eq "Y" || $delete_ftp_files eq "Yes") { 
         print FTP "put -nopreservetime -nopermissions -delete $file$file_extension\n"; 
      
        } 
        else { 
         print FTP "put -nopreservetime -nopermissions $file$file_extension\n"; 
      
        } 
      
       } 
      
       print FTP "\n\n"; 
       print FTP "\# Disconnect\n"; 
       print FTP "close\n\n"; 
       print FTP "\# Exit WinSCP\n"; 
       print FTP "exit\n\n"; 
       close(FTP); 
       runLogger("$pluginname: creating temporary winscp file"); 
      
      }
      ```

   1. 根據ftp_address上的檔案可用性來排程指令碼。
   1. 檔案的命名慣例應為YYYYMMDD-&lt;offline_feed_name>-00。*

1. 將檔案從一個NAS目錄傳輸到其他NAS目錄。

   1. 複製並貼上檔案，直接從另一個NAS目錄連接到一個NAS目錄。 請遵循下列程式：)

      登入伺服器->移至執行-> \\server_name\E$新 [資料夾將會開啟並直接複製或移動檔案]

   1. 使用&quot;copy_files.pl&quot;指令碼將檔案從一個伺服器複製到另一個伺服器，或使用&quot;move_files.pl&quot;將檔案從一個伺服器移動到另一個伺服器。 (這些檔案可在E:\scripts\Scripository中取得)

