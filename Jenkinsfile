pipeline {
    agent any
    parameters([
                    choice(name:"NeedUpgradePC",choices:['yes','no'],description: "Do you need upgrade your PC"),
                    [$class: 'DynamicReferenceParameter',
                            choiceType: 'ET_FORMATTED_HTML',
                            omitValueField: true,
                            description: 'Please provide a Elastic alias label',
                            name: 'PC_RAM',
                            randomName: 'choice-parameter-5631314456178624',
                            referencedParameters: 'NeedUpgradePC',
                            script: [
                                    $class: 'GroovyScript',
                                    fallbackScript: [
                                            classpath: [],
                                            sandbox: true,
                                            script:
                                                    'return[\'nothing.....\']'
                                    ],
                                    script: [
                                            classpath: [],
                                            sandbox: true,
                                            script:
                                                    """
                                    if(NeedUpgradePC.equals('yes')) {
                                        inputBox="<input name='value' type='text' value='Kingston 8GB'>"
                                    } else {
                                        inputBox="<input name='value' type='text' value='Kingston 8GB' disabled>"
                                    }
                                """
                                    ]
                            ]
                         ],
                            [$class: 'DynamicReferenceParameter',
                                    choiceType: 'ET_FORMATTED_HTML',
                                    omitValueField: true,
                                    description: 'Please provide a Elastic alias label',
                                    name: 'PC_CPU',
                                    randomName: 'choice-parameter-5631314456178624',
                                    referencedParameters: 'NeedUpgradePC',
                                    script: [
                                            $class: 'GroovyScript',
                                            fallbackScript: [
                                                    classpath: [],
                                                    sandbox: true,
                                                    script:
                                                            'return[\'nothing.....\']'
                                            ],
                                            script: [
                                                    classpath: [],
                                                    sandbox: true,
                                                    script:
                                                            """
                                    if(NeedUpgradePC.equals('yes')) {
                                        inputBox="<input name='value' type='text' value='Intel Core i5'>"
                                    } else {
                                        inputBox="<input name='value' type='text' value='Intel Core i5' disabled>"
                                    }
                                """
                                            ]
                                    ]
                            ]
     ])
    stages {
        stage('build') {
            steps {
                echo "123"
            }
        }
    }
}
