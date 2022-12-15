pipeline{
  agent any  
  stages{  
     
      stage('Git checkout') {
            steps {
                git branch: 'main', credentialsId: '', url: 'https://github.com/danielbalogun5/ansible_Demo.git'
            }
        }
      stage("Run an ansible playbook"){
        steps{
          ansiblePlaybook credentialsId: 'SSH_KEY', disableHostKeyChecking: true, inventory: 'hosts', playbook: 'nginx_install.yaml'
          //ansiblePlaybook become: true, disableHostKeyChecking: true, inventory: 'hosts', playbook: 'nginx_install.yaml', vaultCredentialsId: 'SSH-KEY'
        }
      }
      stage("Print Nginx Installed"){
        steps{
           sh"echo nginx installed on all servers"
        }
      }
  }
}
