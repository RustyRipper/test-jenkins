pipeline {
    agent any
        stages {
            stage('Parameters'){
                steps {
                    script {
                    properties([
                            parameters([
                                [$class: 'ChoiceParameter', 
                                    choiceType: 'PT_SINGLE_SELECT', 
                                    description: 'Select the Environemnt from the Dropdown List', 
                                    filterLength: 1, 
                                    filterable: false, 
                                    name: 'Lab',
                                    script: [
                                        $class: 'GroovyScript', 
                                        fallbackScript: [
                                            classpath: [], 
                                            sandbox: false, 
                                            script: 
                                                "return['Could not get The environemnts']"
                                        ], 
                                        script: [
                                            classpath: [], 
                                            sandbox: false, 
                                            script: 
                                                'return["vsp0004","vsp0096","os10"]'
                                        ]
                                    ]
                                ],
                                [$class: 'DynamicReferenceParameter', 
                                    choiceType: 'FORMATTED_HTML', 
                                    description: 'Select the AMI from the Dropdown List',
                                    name: 'Version',
                                    referencedParameters: 'Lab',
                                    script: 
                                        [$class: 'GroovyScript', 
                                        fallbackScript: [
                                                classpath: [], 
                                                sandbox: false, 
                                                script: "return['Could not get Environment from Env Param']"
                                                ], 
                                        script: [
                                                classpath: [], 
                                                sandbox: false, 
                                                script: '''
                                                return  "<input name='Aws' value='' class='setting-input' type='text'>"
                                                return  "<input name='Aws2' value='' class='setting-input' type='text'>"
                                                '''
                                            ] 
                                    ]
                                ],
                                [$class: 'DynamicReferenceParameter', 
                                    choiceType: 'ET_ORDERED_LIST', 
                                    description: 'Select the  AMI based on the following information', 
                                    name: 'Image Information', 
                                    referencedParameters: 'Lab, Version',
                                    script: 
                                        [$class: 'GroovyScript', 
                                        script: 'return["Could not get AMi Information"]', 
                                        script: [
                                            script: '''

                                                    return["Your CICD ${Lab} ${Version}".toString()]

                                                    '''
                                            ]
                                        ]
                                ]
                            ])
                        ])
                    }
                }
            }
            stage('print'){
                steps{
                    echo "${Lab}"
                }
            }
        }

}
