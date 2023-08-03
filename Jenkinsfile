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
                                                    return "<ul style="list-style-type: none">
                                                        <li style="padding: 5px">
                                                        <label>VAPP_ID</label>
                                                        <input type="text" class="setting-input" name="value">
                                                          </li>
                                                        </ul>"
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
