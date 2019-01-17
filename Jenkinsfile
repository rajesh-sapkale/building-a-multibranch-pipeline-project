def label = "mypod-${UUID.randomUUID().toString()}"
podTemplate(label: devops, yaml: """
apiVersion: v1
kind: Pod
metadata:
  labels:
    name: sample
spec:
  containers:
  - name: busybox
    image: busybox
    command:
    - cat
    tty: true
"""
) {
    node (devops) {
      container('busybox') {
        sh "hostname"
      }
    }
}
