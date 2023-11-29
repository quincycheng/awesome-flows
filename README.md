# Awesome Flows
- [Awesome Flows](#awesome-flows)
- [Overview](#overview)
- [Use Cases](#use-cases)
  - [Cloud Security](#cloud-security)
    - [Enforcing Zero Trust on Cloud Workload and Secrets](#enforcing-zero-trust-on-cloud-workload-and-secrets)
- [Building Blocks](#building-blocks)
  - [CyberArk](#cyberark)
    - [Conjur Cloud: Get Secrets](#conjur-cloud-get-secrets)
    - [Dynamic Privilege Manager: Get Public Key Script](#dynamic-privilege-manager-get-public-key-script)
  - [Google](#google)
    - [Generative AI: generateText](#generative-ai-generatetext)
  - [ServiceNow](#servicenow)
    - [ServiceNow: CMDB](#servicenow-cmdb)
- [General Instructions](#general-instructions)


# Overview
A Collection of CyberArk Identity Flows by [Quincy Cheng](https://github.com/quincycheng).
- **Use Cases** address real life scenarios.   Most of them connect multiple services to resolve the challenges.  Best for inspiration.
- **Building Blocks** are examples that work with a single services.   Best used as templates.

# Use Cases

## Cloud Security
### Enforcing Zero Trust on Cloud Workload and Secrets

#### Demo
<iframe width="560" height="315" src="https://www.youtube.com/embed/dOGJQk8ndG0?si=cUianjMcWBuYVymF" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

# Building Blocks

## CyberArk 

### Conjur Cloud: Get Secrets
#### Usage
Get a secret from Conjur Cloud
#### Download
[flows/Quincy-ConjurCloud-GetSecret.json](flows/Quincy-ConjurCloud-GetSecret.json)
#### Steps
1. Follow the [General Instruction](#general-instruction)
2. Update the following in the 4th step: "Get Secrets":
   - Hostname (replace apj-secrets with your tenant subdomain)
   - Map > identifier (replace it with the path to Conjur variable)

#### Expected Result
A string that contains the value of the secrets from Conjur Cloud

### Dynamic Privilege Manager: Get Public Key Script
#### Usage
Get the script for apply public key from Dynamic Privilege Manager
#### Download
[flows/Quincy-DPA-GetPublicKeyScriptTemplate.json](flows/Quincy-DPA-GetPublicKeyScriptTemplate.json)
#### Steps
1. Follow the [General Instruction](#general-instruction)
2. Update the following in the 3rd step: "Public-keys Scripts":
   - Hostname (replace apj-secrets with your tenant subdomain)
   - Map > workspaceId (replace it with the ID of the workspace)
   - Map > workspaceType (replace it with the type of the workspace, e.g. AWS)


## Google

### Generative AI: generateText
#### Usage
Allows users to generate text from Google Generative AI by inputting prompts in web form from Flows
#### Download
[flows/Quincy-Google-GenerativeAI-Demo.json](flows/Quincy-Google-GenerativeAI-Demo.json)
#### Demo
<iframe width="560" height="315" src="https://www.youtube.com/embed/0ImLipCehYI?si=usAmTXqxwr_nHx1i" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
#### Steps
Please follow the steps stated in YouTube Video

## ServiceNow

### ServiceNow: CMDB
#### Usage
Connects to ServiceNow API and fetch Linux CI from CMDB

#### Download
[flows/SNOW-CMDB-GetLinuxCI.json](flows/SNOW-CMDB-GetLinuxCI.json)

#### Demo
<iframe width="560" height="315" src="https://www.youtube.com/embed/-iMHaNbpSfc?si=oOPCnQQM4JIEvtfB" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

#### Steps
1. Follow the [General Instruction](#general-instruction)
2. Update the following in the 4th step "Get Secrets":
   - Hostname (replace apj-secrets with your tenant subdomain)
   - Map > identifier (replace it with the path to Conjur variable)
3. Update the following in the 5th step: 
   - Hostname (replace it with your ServiceNow API endpoint)
   - Path (optional, change to another API call if needed)


# General Instructions
1. Download & import the Flows file to your CyberArk Identity Security Platform
2. Inside Identity Admin, Create a service account with appropriate permissions
3. Go to Identity Flows
4. Under "Settings" > "Authoizations", create "new authorizations" with the info from the service account created in previous step
5. Update the following in the 2nd step: "Create Click Token-OAuth2":
   - Authorizations
   - Hostname (replace apj-secrets with your tenant subdomain)
6. Review all steps the update the Hostname (replace apj-secrets with your tenant subdomain)
7. Follow the specific steps stated in the related instructions