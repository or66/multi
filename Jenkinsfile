node {
   def ins = Artifactory.server 'eco'
    //def server = Artifactory.newServer url: 'https://ecosysjfrog.jfrog.io/artifactory', username: 'ortil', password: 'Pass@1234'
        //def ins = Jfrog.instance('free').artifactory()

    def buildInfo1 = Artifactory.newBuildInfo("as","1")
    def uploadSpec = """{
         "files": [
          {
              "pattern": "*.gif",
              "target": "bar-generic/",
              "excludePatterns": ["*.DS_Store"],
                "props": "system-api=https://fishtank.com;version=99.0.3.2;state=incremental;package=mccApp"
            }
         ]
        }"""
      stage ('Clone') {
           //dir('a'){
            git url: 'https://github.com/rms1000watt/hello-world-npm.git'
            // server.setProps spec: uploadSpec, props: "system-api=https:////fishtank.com;version=99.0.3.2;state=incremental;package=mccApp"
        ins.upload spec: uploadSpec, buildInfo: buildInfo1
          // }
       
       
        //   dir('b'){
        //      git url: 'https://github.com/rms1000watt/hello-world-npm.git'
        //   buildInfo2 = server.upload spec: uploadSpec2
        //   buildInfo1.append buildInfo2
        //   }
      }
     
    stage ('publishBI') {
        ins.publishBuildInfo buildInfo1
    //buildInfo = server.upload spec: uploadSpec
    }
 
}
