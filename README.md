# Kubenetes Practice like a beginner
- Manifest file : เป็นตัวบอก structure ทั้งของ resource ที่เราจะสร้าง โดยมีรายละเอียดตาม ตย. ข้างล่าง (IaC หรือ Infrastructure as Code)
    ## Example : 01-pod.ymal
        
        apiVersion : v1
        kind: Pod
        metadata:
            name: linux
            namespace: default
        spec:
            containers:
            - name: busybox
              image: busybox
              command:
              - sleep
              - "3600"
              resources:
                limits:
                    memory: "10Mi"
                    cpu: "100m"
             - name: alpine
               image: alpine
               command:
               - sleep
               - "3600"
               resources:
                limits:
                    memory: "10Mi"
                    cpu: "100m"
- Pod : เป็นหน่วยที่เล็กที่สุดในการ deploy ของ kube เเละส่วนใหญ่ 1 pod = 1 contrainer
    - ไม่ว่าจะมีกี่ contrainer ก็ตาม จะมี id เดียวที่ไม่มีใครสามารถ access มันได้ 
![podHost](https://platform9.com/wp-content/uploads/2019/05/kubernetes-Pod-architecture.jpg)
    