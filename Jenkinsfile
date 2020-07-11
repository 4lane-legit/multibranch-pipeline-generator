//https://github.com/jenkinsci/job-dsl-plugin/wiki/User-Power-Moves
node {
    label "any"
    properties([pipelineTriggers([pollSCM('')])])
    checkout scm
    jobDsl targets: ['jobs/*.groovy'].join('\n'),
        removedJobAction: 'DELETE',
        removedViewAction: 'DELETE'
}
