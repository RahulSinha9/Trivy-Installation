## Trivy-Installation:

<details><summary><b>Install Trivy</b></summary>
  
```bash
sudo apt-get install wget apt-transport-https gnupg lsb-release
```

```bash
wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | gpg --dearmor | sudo tee /usr/share/keyrings/trivy.gpg > /dev/null
```

```bash 
echo "deb [signed-by=/usr/share/keyrings/trivy.gpg] https://aquasecurity.github.io/trivy-repo/deb $(lsb_release -sc) main" | sudo tee -a /etc/apt/sources.list.d/trivy.list
```

```bash
sudo apt-get update
```

```bash
sudo apt-get install trivy
```
</details>

<details><summary><b>Trivy Commands</b></summary>

```bash
trivy image imagename
```

```bash
trivy fs --security-checks vuln,config   Folder_name_OR_Path
```

```bash
trivy image --severity HIGH,CRITICAL image_name
```

```bash
trivy image -f json -o results.json image_name
```

```bash
trivy repo repo-url
```

```bash
trivy k8s --report summary cluster
```
</details>
