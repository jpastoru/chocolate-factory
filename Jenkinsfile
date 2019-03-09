def gitUrl = "https://github.com/jpastoru/chocolate-factory.git"
def BRANCH_NAME = "master"
node {
    stage("checkout git") {
      dir("${WORKSPACE}") {
          git url: "${gitUrl}", branch: "${BRANCH_NAME}"
          sh "ls -la"
      }
    }

    stage("Lint") {
      dir("${WORKSPACE}") {
        println("TODO: Add lint")
      }
    }

    stage("Unit Test") {
      dir("${WORKSPACE}") {
        withMaven( maven: "M3") {
          sh "mvn test"
        }
      }
    }

    stage("build") {
      dir("${WORKSPACE}") {
        withMaven( maven: "M3") {
          sh "mvn install"
        }
      }
    }

    stage("Integration Test") {
      dir("${WORKSPACE}") {
        println("TODO: integration test")
      }
    }


    stage("deploy") {
      println("deploy delicious chocolate!!")
    }

}
