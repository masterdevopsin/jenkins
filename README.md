1. create an instnace with network as https
2. install jdk and jenkins
3. create a github repo
4. open vs code---open new window using---cmnd +shift +n
5. click on clone github repo and pass the github link so githup repo      is cloned
6. Install eithor of below extension in vs code for healthy environment , syntax highlighters , auto fll suggestions etc while writing jenkins pipeline 
7. Install vs code extension called --- jenkins jack  or 
8. U can also install the extension called JenkinsFile support
9. type pipeline and u can see the suggestion appear and if you click on the suggestion you will get to see entire jenkins pipeline skeleton
10. press ctrl+space to get the autofill suggestion
11. Now start writing pipeline
12. Pipelines are 2 types 
        1. Scripted pipeline
        2. Declarative pipeline
13. Scripted pipeline is old method and its syntax be like 
        node {

        }
14. Declarative pipeline is currently used one and its syntax be like
        pipeline  {

        }
15. Within this pipeline { } u have stages { } , stage() and steps
        pipeline  {
                stages {
                    stage('stage 1') {
                        steps {
                            sh 'sleep 5'
                            echo "this is stage 1"
                        }
                    }
                    stage('stage 2') {
                        steps {
                            sh '''
                                #!/bin/bash
                                pwd
                                ls -lrt
                                sleep 5
                            '''
                        }
                    }
                }

        }

16. This is the mandatory skeleton u have for every pipeline

17. nowif u want to specify in which node ur job should run then u have to specify this within pipeline accordingly
            agent any
            agent slave-label

18. agent any = hey jenkins run this job in any healthy slave node
        pipeline {
            agent any

            stages {
                
            }
        }

19. Git commit :
    i created a file called gitcp where i configured a script to execute git push pull etc like

#!/usr/bin/env bash
tmpstmp="$(date +'%d-%B-%y %I:%M%p')"
git pull &&
git add --all &&
git commit -m "$* ${tmpstmp}" &&
git push &&
echo "pushed : $* $tmpstmp"

20. now since no commits are made we have to do all process manually for first time , i.e 
    git status
    git add .
    git commit -m "message"
    git push -u origin main


