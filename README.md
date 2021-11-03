### React Multi Page Web Template 1

### How to use

```
yarn install
yarn start
```

### Tutorial

- React Router: enable multipage on react
- How to make React App

```
# install node.js, yarn, Editor follow by access to certain folder
yarn global add create-react-app
create-react-app react-multi-page-web-template-1
# access to react
cd react-multi-page-web-template-1
```

- Install React Router Dom

```
yarn add react-router-dom
# https://github.com/ndb796/React-Multi-Page-Web-Template-1/commit/94ee6fa902f12271a12c45a8a186296eab454412
# /, /about, /faq 경로로 테스트
```

- Add Header & Header Design

```
# https://github.com/ndb796/React-Multi-Page-Web-Template-1/commit/00bb34a56d116cc28ceec955ed551b61e5a9c834
# https://github.com/ndb796/React-Multi-Page-Web-Template-1/commit/bcfbe19ba46b7a06e0f51e7ac1ca797406c0906f
```

- Add Q/A & Q/A Design

```
# https://github.com/ndb796/React-Multi-Page-Web-Template-1/commit/d7e9c89a54178e3122276fb3e11eed8899d6b54f
# https://github.com/ndb796/React-Multi-Page-Web-Template-1/commit/192a69d04926a18297ce9f49c38824dee4bb305c
```

- Add Board & Detail Routing

```
# https://github.com/ndb796/React-Multi-Page-Web-Template-1/commit/f794ffff1d5c03a171640ab27ce094ee150a0790
# https://github.com/ndb796/React-Multi-Page-Web-Template-1/commit/5bb62f2cdd0086234d493231ee668824e328de61
```

- Get FAQ From Firebase

![image](https://user-images.githubusercontent.com/16822641/58227791-530d6100-7d67-11e9-8649-3646825e1829.png)

```
# https://github.com/ndb796/React-Multi-Page-Web-Template-1/commit/b86d59e512fae01361a2dfa8f0e2056c7d18ebe8
```

- Get About From Firebase

![image](https://user-images.githubusercontent.com/16822641/58228027-39204e00-7d68-11e9-9ba1-10454f82e790.png)

```
# https://github.com/ndb796/React-Multi-Page-Web-Template-1/commit/96e0e447c37149fdf94609556b8d62885da4f375
```

- Add Notice

![image](https://user-images.githubusercontent.com/16822641/58541388-62445100-8236-11e9-8278-6188bffa5fde.png)

```
# https://github.com/ndb796/React-Multi-Page-Web-Template-1/commit/fd612e717ac385a17b82ef9d07da58a582fc3691
```

- Add Multi Language Support

```
yarn add react-i18next
yarn add i18next
yarn add i18next-browser-languagedetector
```

- Deploy on AWS Cloud Front

```
yarn build
# check ./build folder
# create AWS S3 Bucket
# name: www-deploy-test (Only Next)
# [Upload] all the build files
# [Properties] - [Static website hosting] - [Use this bucket to host a website] - index: index.html, error: index.html
# Open endpoint URL - 403 Forbidden Error
# change policy of burcket
# [Block public access] - Off [Block public access to buckets and objects granted through new public bucket policies]
# [Block public access] - Off [Block public and cross-account access to buckets and objects through any public bucket policies]
# [Bucket Policy]
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AddPerm",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::www-deploy-test/*"
            ]
        }
    ]
}
# Open endpoint URL - 200
# [Cloud Front] - [Create Distribution] - Web [Get Started] - Origin Domain Name selection - [Redirect HTTP to HTTPS] - Default Root Object: index.html - [Create Distribution]
# finish setting CDN after 10 minutes
# [Network] indentify x-cache: Hit from cloudfront
```
