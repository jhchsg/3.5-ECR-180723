# 3.5-ECR-180723
PS C:\Users\jhchs\3.5-ECR-180723> aws ecr get-login-password --region ap-southeast-1 | docker login --username AWS --password-stdin 255945442255.dkr.ecr.ap-southeast-1.amazonaws.com
Login Succeeded

Logging in with your password grants your terminal complete access to your account.
For better security, log in with a limited-privilege personal access token. Learn more at https://docs.docker.com/go/access-tokens/
PS C:\Users\jhchs\3.5-ECR-180723> docker build -t 3.5-ecr-repo:latest .
[+] Building 2.1s (11/11) FINISHED                                                         docker:default
 => [internal] load .dockerignore                                                                    0.0s
 => => transferring context: 67B                                                                     0.0s
 => [internal] load build definition from Dockerfile                                                 0.0s
 => => transferring dockerfile: 332B                                                                 0.0s
 => [internal] load metadata for docker.io/library/node:16-alpine                                    2.0s
 => [auth] library/node:pull token for registry-1.docker.io                                          0.0s
 => [1/5] FROM docker.io/library/node:16-alpine@sha256:6c381d5dc2a11dcdb693f0301e8587e43f440c90cdb8  0.0s
 => [internal] load build context                                                                    0.0s
 => => transferring context: 11.85kB                                                                 0.0s
 => CACHED [2/5] WORKDIR /my-app                                                                     0.0s
 => CACHED [3/5] COPY package*.json ./                                                               0.0s
 => CACHED [4/5] RUN npm install                                                                     0.0s
 => CACHED [5/5] COPY . .                                                                            0.0s
 => exporting to image                                                                               0.0s
 => => exporting layers                                                                              0.0s
 => => writing image sha256:85360dcfd57ec72a29234dfc17ea4fd057cf09499c51242a31bfbfb435f562de         0.0s
 => => naming to docker.io/library/3.5-ecr-repo:latest                                               0.0s
PS C:\Users\jhchs\3.5-ECR-180723> docker tag 3.5-ecr-repo:latest 255945442255.dkr.ecr.ap-southeast-1.amazonaws.com/3.5-ecr-repo:latest
PS C:\Users\jhchs\3.5-ECR-180723> docker push 255945442255.dkr.ecr.ap-southeast-1.amazonaws.com/3.5-ecr-repo:latest
The push refers to repository [255945442255.dkr.ecr.ap-southeast-1.amazonaws.com/3.5-ecr-repo]
3065ddd05f7a: Pushed
d15e01510178: Pushed
3c8c1d729662: Pushed
f2577dee709a: Pushed
7b71a9bb851a: Pushed
323c772d0cd8: Pushed
87820ee0191d: Pushed
78a822fe2a2d: Pushed
latest: digest: sha256:76e0f471a49ea675d89b29f9a265581c1aee70c4aa4f5428fb1a9688aa3d41ea size: 1993
PS C:\Users\jhchs\3.5-ECR-180723>