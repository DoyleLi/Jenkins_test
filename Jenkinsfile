println env.JOB_NAME
println env.BUILD_NUMBER

build_ok = true
fail_stage = ""
pipeline {
    agent { label 'ubuntu_linux' }

    options {
        durabilityHint 'PERFORMANCE_OPTIMIZED'
        timeout(time:16, unit: 'HOURS')
        timestamps()
    }

	environment {
		def NUMBER = sh(script: "expr ${env.BUILD_NUMBER}", returnStdout: true).trim()
		def TIMESTEMP = sh(script: "date +%s", returnStdout: true).trim()
		def DATESTEMP = sh(script: "date +\"%Y-%m-%d\"", returnStdout: true).trim()
	}
	
    stages {
		stage("Tools") {
            steps {
                echo '+++ Tolls start +++' 
                echo '--- Tolls finish ---' 
            }
        }
		
		stage("LLVM-git-monorepo") {
            steps {
                echo '+++ LLVM-git-monorepo start+++'
                echo '--- LLVM-git-monorepo finish ---'
            }
        }
    }
}
