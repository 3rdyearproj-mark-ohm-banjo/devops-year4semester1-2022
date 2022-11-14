kubernetes

```bash
kubectl apply -f k8s-basic/
kubectl apply -f frontend.yaml
kubectl delete -f k8s-basic/
kubectl delete -f ./
```

<br>

Helm

```bash
helm list
helm install -f pathValue ชื่อrelease pathHelmChart   //ใช้ครั้งแรก
helm upgrade -f pathValue ชื่อrelease pathHelmChart   //ใช้ครั้งที่สองเป็นต้นไป
helm uninstall ชื่อrelease   //ลบออก
helm downgrade -f pathValue ชื่อrelease pathHelmChart

# ตัวอย่าง
helm install -f k8s-helm/helm-values/values-smb-dev.yaml sharemybook k8s-helm/helm --namespace=smb-workload
helm install -f k8s-helm-ssl/helm-values/values-smb-dev.yaml sharemybook k8s-helm-ssl/helm --namespace=smb-workload
helm upgrade -f k8s-helm-ssl/helm-values/values-smb-dev.yaml sharemybook k8s-helm-ssl/helm --namespace=smb-workload 
helm upgrade -f k8s-helm-ssl/helm-values/values-smb-dev.yaml --set extraEnv.COMMIT_ID=bb  sharemybook k8s-helm-ssl/helm --namespace=smb-workload 
helm uninstall sharemybook --namespace=smb-workload 
```

<br>



#  Azure CLI Terraform

https://acloudguru.com/blog/engineering/the-ultimate-terraform-cheatsheet <br>
คำสั่งที่ใช้บ่อย
```
terraform init   //ใช้ตอนแรกสุด
terraform init -reconfigure    //ใช้ตอนที่มีconfigใหม่ๆเพิ่มขึ้นมา
terraform plan     //ตรวจสอบการทำงาน
terraform apply      
terraform destroy
```
<br>

# Variable

https://acloudguru.com/blog/engineering/the-ultimate-terraform-cheatsheet <br>
คำสั่งที่ใช้ร่วมกับVariable Files ถ้าไม่ใส่มันจะไม่มีvaluesนั้น ทำให้ตอนเรารัน เราต้องกำหนดvaluesเอง
```
terraform init   //ใช้ตอนแรกสุด
terraform init -reconfigure    //ใช้ตอนที่มีconfigใหม่ๆเพิ่มขึ้นมา
terraform plan -var-file="var.tfvars"   //ตรวจสอบการทำงาน
terraform apply -var-file="var.tfvars"
terraform destroy -var-file="var.tfvars"
```
https://www.terraform.io/language/configuration-0-11/variables <br>
### มีหลายวิธีในการทำ แต่อันนี้ใช้วิธีสร้าง Variable Files ขึ้นมา
ในไฟล์ eks.tf และ nlb.tf จะมี Variable อยู่เรียกว่า ***Input variables*** ซึ่งสามารถนำไปใช้งานได้ <br>
ไฟล์ var.tfvars เป็น ***Values*** ที่ส่งค่าไปหา Input variables





░░░░░░░░░░░░░░░░░░░░░▄▀░░▌  <br>
░░░░░░░░░░░░░░░░░░░▄▀▐░░░▌  <br>
░░░░░░░░░░░░░░░░▄▀▀▒▐▒░░░▌  <br>
░░░░░▄▀▀▄░░░▄▄▀▀▒▒▒▒▌▒▒░░▌  <br>
░░░░▐▒░░░▀▄▀▒▒▒▒▒▒▒▒▒▒▒▒▒█   <br>
░░░░▌▒░░░░▒▀▄▒▒▒▒▒▒▒▒▒▒▒▒▒▀▄   <br>
░░░░▐▒░░░░░▒▒▒▒▒▒▒▒▒▌▒▐▒▒▒▒▒▀▄   <br>
░░░░▌▀▄░░▒▒▒▒▒▒▒▒▐▒▒▒▌▒▌▒▄▄▒▒▐    <br>
░░░▌▌▒▒▀▒▒▒▒▒▒▒▒▒▒▐▒▒▒▒▒█▄█▌▒▒▌   <br>
░▄▀▒▐▒▒▒▒▒▒▒▒▒▒▒▄▀█▌▒▒▒▒▒▀▀▒▒▐░░░▄   <br>
▀▒▒▒▒▌▒▒▒▒▒▒▒▄▒▐███▌▄▒▒▒▒▒▒▒▄▀▀▀▀    <br>
▒▒▒▒▒▐▒▒▒▒▒▄▀▒▒▒▀▀▀▒▒▒▒▄█▀░░▒▌▀▀▄▄    <br>
▒▒▒▒▒▒█▒▄▄▀▒▒▒▒▒▒▒▒▒▒▒░░▐▒▀▄▀▄░░░░▀    <br>
▒▒▒▒▒▒▒█▒▒▒▒▒▒▒▒▒▄▒▒▒▒▄▀▒▒▒▌░░▀▄      <br>
▒▒▒▒▒▒▒▒▀▄▒▒▒▒▒▒▒▒▀▀▀▀▒▒▒▄▀     <br>

<br>
<br>

░░░░░░░░░░██░░░░░░░░░░██   <br>
░░░░░░░░██░░██░░░░░░██░░██   <br>
░░░░░░░░██░░▒▒██████▒▒░░██   <br>
░░░░░░██▒▒░░░░▒▒▒▒▒▒░░░░▒▒██   <br>
░░░░░░██░░░░░░░░░░░░░░░░░░██   <br>
░░░░██▒▒░░░░░░░░░░░░░░░░░░▒▒██   <br>
░░░░██░░░░██░░░░██░░░░██░░░░██   <br>
░░░░██░░▒▒░░░░██░░██░░░░▒▒░░██   <br>
░░██▒▒░░░░░░░░░░░░░░░░░░░░░░▒▒██   <br>
░░██▒▒░░░░░░░░░░░░░░░░░░░░░░▒▒██  <br>
░░██░░░░░░░░░░░░░░░░░░░░░░░░░░██  <br>
░░██░░░░░░░░░░░░░░░░░░░░░░░░░░██   <br>
██▒▒▒▒░░░░░░░░░░░░░░░░░░░░░░▒▒▒▒██   <br>
██▒▒░░░░░░░░░░░░░░░░░░░░░░░░░░▒▒██   <br> 
██░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░██░░░░████   <br>
██▒▒▒▒░░░░░░░░░░░░░░░░░░░░░░▒▒▒▒██░░██░░░░██  <br>
██▒▒░░░░░░░░░░░░░░░░░░░░░░░░░░▒▒██░░░░██▒▒██  <br>
██░░░░░░██░░░░░░░░░░░░░░██░░░░░░██░░░░██░░██  <br>
██▒▒░░░░██░░██░░░░░░██░░██░░░░▒▒██████░░░░██  <br>
░░██▒▒░░██░░██░░░░░░██░░██░░▒▒██░░░░▒▒░░██   <br>
░░░░██████░░██████████░░████████████████   <br>
░░░░░░░░██████░░░░░░██████   <br>