Vagrant.configure('2') do |config|
    config.vm.box = 'azure'
    config.vm.boot_timeout = 1200

    config.vm.provider :azure do |azure|

        #full path to pem file
        azure.mgmt_certificate = File.expand_path('C:\Users\JJJR\.ssh\azurevagrant.key')
        azure.mgmt_endpoint = 'https://management.core.windows.net'

        ##to get this run: azure account list
        azure.subscription_id = '5fef723c-3a54-4877-a66b-c340d9ed4fe8'

        azure.storage_acct_name = 'azurevagrant' # optional. A new one will be generated if not provided.

        ##to get this run: azure vm image list | Select-String "Datacenter" | Select-String "2012"
        azure.vm_image    = 'a699494373c04fc0bc8f2bb1389d6106__Windows-Server-2012-Datacenter-20150916-en.us-127GB.vhd'

        azure.vm_user = 'vagrant' # defaults to 'vagrant' if not provided
        azure.vm_password = 'vagrant123#@!' # min 8 characters. should contain a lower case letter, an uppercase letter, a number and a special character

        azure.vm_name = 'azurevagrant' # max 15 characters. contains letters, number and hyphens. can start with letters and can end with letters and numbers
        azure.cloud_service_name = 'azurevagrant' # same as vm_name. leave blank to auto-generate

        ##to get this run: azure vm location list
        azure.vm_location = 'North Europe'

        azure.tcp_endpoints = '3389:53389' # opens the Remote Desktop internal port that listens on public port 53389. Without this, you cannot RDP to a Windows VM.
        azure.winrm_https_port = 5986

        azure.winrm_transport = %w(https)
  end

end