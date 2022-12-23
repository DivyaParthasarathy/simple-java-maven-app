pipeline {
    agent any
    stages {
        stage ('Clone') {
            steps {
                git branch: 'PipelineTest', url: "https://github.com/DivyaParthasarathy/simple-java-maven-app.git"
            }
        }

        
        stage ('Exec Maven') {
            steps {
                rtMavenRun (
                    tool: MAVEN_TOOL, // Tool name from Jenkins configuration
                    pom: 'pom.xml',
                    goals: 'clean install',
                    deployerId: "MAVEN_DEPLOYER",
                    resolverId: "MAVEN_RESOLVER"
                )
            }
        }

    }
}
