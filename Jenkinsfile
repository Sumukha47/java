node('slave2') {
    def gitrepo = "https://github.com/TAPASHRANJANNANDI/java-project.git"
    def gitbranch = "master"
    def stages = ["git-clone" , "compile" , "run"]
    try {
    for (s in stages) {
        stage(s) {
            if (s == "git-clone") {
                git branch: gitbranch , url: gitrepo 
                }
            if (s == "compile"){
               sh '''javac Test.java'''
            }
            if (s == "run") {
                sh '''java Test.java'''
            }
        }
    }
     mail bcc: '', body: '''This is a successful build. 
''', cc: 'nanditapashranjan35@gmail.com', from: '', replyTo: '', subject: 'success mail jenkins - Tapash', to: 'sumukhu6@gmail.com'
    } 
catch(Exception e) {
      mail bcc: '', body: '''This is a failed build. 
''', cc: 'nanditapashranjan35@gmail.com', from: '', replyTo: '', subject: 'failure mail jenkins - Tapash', to: 'sumukhu6@gmail.com'
throw e
    
}    
 
    
    
}

