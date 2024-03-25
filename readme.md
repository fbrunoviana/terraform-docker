# Using Terraform with a container Docker

If you don't have install terraform on your desk, but docker yes!

![Visualize a wide banner format, focusing on a sleek, modern workspace ambiance. The central piece is a panoramic computer screen showcasing an expansive view of Terraform code, with syntax highlighting that makes the Terraform-specific elements pop. The Terraform logo is prominently displayed at the corner of the screen, asserting the theme. The Docker logo, stylized as a subtle, artistic wave, merges seamlessly into the background, ensuring Terraform takes the main stage. Git elements, like branches and commit icons, are elegantly integrated into the edges of the image, framing the central focus on Terraform. This composition highlights the use of Terraform within a Docker and Git ecosystem, tailored for a tech-savvy audience.](img/banner.png)

1. Build the image: `docker build -t terraform-code:v1.0`
2. We need to instantiate a new container of this image: `docker run -it -d --name tfapp terraform-code:v1.0 /bin/bash`
3. We can execute the Terraform commands in our container using:
```
docker exec tfapp terraform init
docker exec tfapp terraform plan
docker exec tfapp terraform apply --auto-approve
```
4. We can test using: `docker exec tfapp cat /root/guelo`