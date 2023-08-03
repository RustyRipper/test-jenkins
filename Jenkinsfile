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
                                    choiceType: 'ELEMENT_TYPE_FORMATTED_HTML', 
                                    description: 'Select the  AMI based on the following information', 
                                    name: 'Image Information', 
                                    referencedParameters: 'Lab',
                                    script: 
                                        [$class: 'GroovyScript', 
                                        script: 'return["Could not get AMi Information"]', 
                                        script: [
                                            script: '''

                                                    return "<input type="text" class="setting-input" name="value">"

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
