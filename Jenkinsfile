//写流水线的脚本（声明式、脚本式）
pipeline{
    //全部的CICD流程都需要在这里定义

    //任何一个代理可用就可以执行
   // agent none  //以后所有stage都必须指定自己的
    agent any




    //定义一些环境信息
    environment {
      hello = "123456"
      world = "456789"
      WS = "${WORKSPACE}"
      IMAGE_VERSION = "v1.0"


    }

    //定义流水线的加工流程
    stages {
        //流水线的所有阶段
        stage('环境检查'){
            steps {
               sh 'printenv'
               echo "正在检测基本信息"
               sh 'java -version'
               sh 'git --version'
               sh 'docker version'
               sh 'pwd && ls -alh'
               sh "echo $hello"
               //未来，凡是需要取变量值的时候，都用双引号
               sh 'echo ${world}'

            }
        }
        //1、编译 "abc"
        stage('maven编译'){
            //jenkins不配置任何环境的情况下， 仅适用docker 兼容所有场景

            steps {

                   echo "编译..."



            }
        }

        //2、测试，每一个 stage的开始，都会重置到默认的WORKSPACE位置
        stage('测试'){
            steps {
            echo "测试"

            }
        }

        //3、打包
        stage('生成镜像'){
            steps {
                echo "打包..."
                //检查Jenkins的docker命令是否能运行

                sh 'pwd && ls -alh'


                //镜像就可以进行保存


            }
        }



         stage('推送镜像'){


             steps {
                //false就直接结束

                echo "$APP_VER"



         }
}





    }


}
