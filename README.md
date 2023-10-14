# "Unite through Creativity: Building Dreams in Minecraft"
![Minecraft Logo](https://logos-world.net/wp-content/uploads/2020/05/Minecraft-Logo.png)
---
## Motivation
### Introduction
In these challenging times, the children of Israel have faced unique and unforeseen difficulties. 
However, within these struggles, there is an opportunity to foster resilience, creativity, and unity. 
We believe that by bringing all the children of Israel together, regardless of their background, 
we can create a platform where they can express their creativity and build a brighter future, brick by brick.

### Project Overview
We are excited to introduce a free, community-driven project dedicated to all the children of Israel. 
Our goal is to provide a space where kids can come together, play, and create within the virtual realm of Minecraft. 
We believe that this platform will not only allow them to bond with their classmates but also serve as an outlet 
for their creativity during these trying times.

### Key Objectives
1. **Foster Unity:** Our project aims to bring children from diverse backgrounds together. 
By playing Minecraft as a community, they can build connections, understanding, and friendships that transcend borders.

2. **Encourage Creativity:** Minecraft is a canvas for imagination. Through this project, we hope to inspire the 
children of Israel to express their creativity, build incredible structures, and embark on exciting adventures.

3. **Support Education:** We believe that Minecraft can be a powerful educational tool. 
Children can learn important skills such as teamwork, problem-solving, and even gain insights into 
architecture, design, and resource management.

4. **Promote Resilience:** By creating, overcoming challenges, and working as a team, children can develop resilience, 
which is essential in navigating these hard times.

### Project Features
- **Community Servers:** We will provide dedicated servers where children can play with their classmates, 
collaborate on projects, and make new friends from across the nation.

- **Weekly Challenges:** To keep the creativity flowing, we will introduce weekly challenges that encourage kids 
to build, explore, and learn within the Minecraft world.

- **Mentorship:** Experienced Minecraft players and educators will be available to guide and mentor children, 
ensuring a safe and positive online environment.

- **Art and Storytelling:** Beyond construction, we will also encourage artistic expression and 
storytelling within Minecraft, letting children share their unique narratives.

- **Virtual Events:** Periodic events and competitions will add excitement and variety to the platform.

### How You Can Support
We invite you to be a part of this heartwarming initiative. 
Your support, whether through donations, volunteering, or spreading the word, 
can help us create a vibrant, inspiring, and safe space for the children of Israel during these challenging times.

### Conclusion
"Unite through Creativity: Building Dreams in Minecraft" is more than just a gaming platform; 
it's a space for children to find solace, inspiration, and unity in the face of adversity. 
Together, we can provide them with an opportunity to escape into a world where they can build their dreams, 
forge connections, and learn valuable life skills. Join us in supporting the children of Israel as they navigate 
these hard times and emerge stronger, more creative, and more united than ever before.

## Technology
The purpose of this repository is to define a standalone, fully functioning and secure AWS EKS cluster that is able to
provision persistent Minecraft servers (Java & Bedrock) serially and in a scalable fashion.
> The intention of this initiative would benefit from the resources created here to be OSS thus enabling any organization
> to take part to deploy the functionality at their own discretion

The technical contents of this repository can be divided into three main sections
1. Kubernetes, provisioned using Terraform, running as a managed AWS EKS service. This provides the foundation and 
the orchestration needed to execute the compute resources and provide safe and secure connectivity to the public.
2. Helm is used to provision Kubernetes services which comprises the infrastructure `system` resources as well as
the servers themselves
3. The Minecraft server itself, which comes wrapped in a Docker image and declared using a Helm chart is based on an
OSS [project](https://docker-minecraft-server.readthedocs.io/en/latest/).

### Installation
The Terraform module declares a standalone EKS cluster as well as the necessary supporting infrastructure and VPC.
In order to provision the cluster execute the following command:
```shell
cd eks-minecraft
terraform plan -out plan
terraform apply "plan" 
```
