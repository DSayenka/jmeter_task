node {
 stage('clone git repo'){
 git 'https://github.com/DSayenka/jmeter_task.git'
 }

 stage("configure") {
        sh "mkdir $WORKSPACE/$BUILD_NUMBER/"
    }

 stage('run test'){
 sh "mkdir /tmp/reports"
 sh "cd D:/My Documents/Training courses/Performance testing/apache-jmeter-5.5/bin"
      sh "jmeter -Jjmeter.save.saveservice.output_format=xml -n -t Darya Sayenka_Task Plan_v3.jmx -l /tmp/reports/JMeter.jtl -e -o /tmp/reports/HtmlReport"
 }

 stage('publish results'){
 sh "mv /tmp/reports/* $WORKSPACE/$BUILD_NUMBER/"
 archiveArtifacts artifacts: '$WORKSPACE/$BUILD_NUMBER/JMeter.jtl, $WORKSPACE/$BUILD_NUMBER/HtmlReport/index.html'
 }
}
