pipeline {
  parameters {
    activeChoiceParam('deploy') {
      choiceType('RADIO')
      groovyScript {
        script("return ['true', 'false']")
        fallbackScript("return ['error']")
      }
    }
    stringParam('Azure', '', '')
    activeChoiceReactiveReferenceParam('Aws') {
      choiceType('FORMATTED_HTML')
      groovyScript {
        script('''
        if (!deploy.equals('true')) {
          return  "<input name='Aws' value='' class='setting-input' type='text'>"
        }
        '''
        )
        fallbackScript("return ['error']")
      }
      referencedParameter('deploy')
    }
}
  stages{
    stage('build') {
      steps {
        script {
          echo 'Running.'
        }
      }
    }
  }
}
