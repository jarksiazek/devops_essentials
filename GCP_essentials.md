<details><summary>everything about roles</summary>
<p>
  * https://cloud.google.com/iam/docs/understanding-roles
</p>
</details>

<details><summary>sdk commends</summary>
<p>

- login into GCP selecting user from browser
```bash
gcloud auth
```
- login into GCP using user
```bash 
gcloud auth login ACCOUNT
```
- login into GCP using service account
```bash
gcloud auth activate-service-account "emed-step-admin-serviceaccount@emed-step-admin.iam.gserviceaccount.com" --key-file=emed-step-admin-c50d02e46a7d.json
```
</p>
</details>

<details><summary>compute resources</summary>
<p>
![image](https://github.com/user-attachments/assets/b207756c-c75c-46ab-b26d-ad6438dd4ef3)


- Compute engine
  - IAAS Solution
  - Linux and Windows
  - Custom machine (RAM, CPU, Hard Drive)
- GKE 
- App Engine (GAE)
  - PAAS Solution - fully managed service
  - deploy web app at high scale
- Cloud Run
  - PAAS Solution - fully managed service
  - containered applications
  - Best of (GEA + container)
  - Next generation of GAE
- Cloud Functions
  - Serverless
  - something like AWS lambda 
</p>
</details>
