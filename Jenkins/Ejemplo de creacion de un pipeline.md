# Configuración pipeline

Step
Son las tareas ó comandos que ejecutados de forma secuencial implementan la lógica de nuestro flujo de trabajo. Por ejemplo, un comando puede ser la escritura de un mensaje en la consola echo 'Mensaje de prueba' ó por ejemplo la descarga de un repositorio checkout scm.

Node
Los nodos son agrupaciones de tareas o steps que comparten un workspace. Los conjuntos de steps son añadidos a la cola de Jenkins para ser ejecutados cuando haya algún espacio libre entre los agentes de ejecución. Los agentes de ejecución pueden ser la misma máquina del servidor maestro de Jenkins o un Jenkins en otra máquina en modo esclavo dedicado a este propósito.

Es importante reseñar que el directorio de trabajo (workspace) es compartido por los steps del nodo, de forma que steps de un nodo pueden acceder a ficheros/directorios generados por steps de ese mismo nodo. Por el contrario un step de un nodo no puede acceder al workspace de otro nodo.

Stage
Son las etapas lógicas en las que se dividen los flujos de trabajo de Jenkins. Cada stage puede estar compuesto por un conjunto de steps, y cada node puede contener un conjunto de stages.

Es una práctica recomendada dividir nuestro flujo de trabajo en etapas ya que nos ayudará a organizar nuestros pipelines en fases. Además Jenkins nos muestra los resultados de la ejecución del pipeline divido en etapas, mostrando el resultado de la ejecución de cada una de ellas con un código de colores.

- EJEMPLO:
  Con este ejemplo se puede correr con diferentes comandos diferentes endpoint de un proyecto de API services, ademas de clonar el repositorio.

```shell
pipeline {
    agent any
    tools {
        maven 'Maven 3.8.1'
        jdk 'java 8'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Clone Code') {
            steps {
                echo 'Cloning the project Code'
               checkout([$class: 'GitSCM', branches: [[name: '*/develop']], extensions: [], userRemoteConfigs: [[credentialsId: '2808a65c-e4ff-4fa3-a3a4-67814951d527', url: 'https://andres_rios@bitbucket.org/zemoga/fsbp_api_automation_rest_assured.git']]])
            }
        }

        stage ('Build Documents_Search') {
            steps {
                echo 'Building Maven project'
                sh 'mvn test -Dtest=Get_Documents_Search'
            }
        }

        stage ('Build Categories') {
            steps {
                echo 'Building Maven project'
                sh 'mvn test -Dtest=Get_Categories'
            }
        }

        stage ('Build Documents_Search_Suggestions') {
            steps {
                echo 'Building Maven project'
                sh 'mvn test -Dtest=Get_Documents_Search_Suggestions'
            }
        }

        stage ('Build Filters') {
            steps {
                echo 'Building Maven project'
                sh 'mvn test -Dtest=Get_Filters'
            }
        }
    }
}
```

![Image text](https://github.com/andres4715-gif/importanDocuments/blob/master/imagenes/jenkins.png)
