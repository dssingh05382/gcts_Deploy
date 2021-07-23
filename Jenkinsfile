library('piper-lib-os') _

stage('Prepare') {
  node {
    deleteDir()
    checkout scm
    setupCommonPipelineEnvironment script:this    
  }
}  
  
stage('Build') {

}

stage('Deploy Commit') {
  node {
    gctsDeploy(
      script: this,
      host: 'http://172.16.10.101:8000',
      client: '100',
      abapCredentialsId: 'ABAPUserPasswordCredentialsId',
      repository: 'skondekar-shubh',
      remoteRepositoryURL: "https://github.com/skondekar/shubh",
      role: 'TARGET',
      vSID: 'S4D',
      branch: 'master',
      commit: 'commit',
      scope: 'scope',
      rollback: false,
      verbose: true,
      configuration: [dummyConfig: 'dummyval']   
    )
  }    
}
