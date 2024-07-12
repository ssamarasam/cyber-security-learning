# OWASP Top 10 for Large Language Model(LLM) Applications   - from Linkedin Learning

Note: released on Aug 2023

### 1. Prompt Injection attack

When attackers manipulate the output of an LLM by creating a harmful command that causes the model to ignore the rules or guidelines set by the creator
- to gain unauthorized access to information or to manipulate data in the llm
- harmful commands
- manipulated external inputs - plugins, extensions, addons, additional modules interact with langauge model
- exfiltration, data theft
- > ensure prompts are validated throughly and sanitized

### 2. Insecure Output handling
- exploiting using cross site scripting
> establish zero trust between llm and your downstream
> validate llm input, keep an eye on the expected content/length


### 3. Training data poisoning

LLM build and deployment process
1. gather data
2. label data
3. train the model
4. evaluate the model
5. deploy the model
- label poisoning
- spam label poisoning


### 4. Model Denial of Service
- utilizing botnet for dos attacks to llm service
> limiting the size and type of input allowed
> monitor resource utilization
> user management protocols

### 5. Supply Chain Vulnerability
Supply chain attacks/buls:
- weaknesses or risks within the end to end process of creating, distributing and maintaing products and services
- e.g solarwinds attack (not related to LLM )
- attcks focused on suppliers code
- 50% attributed to APT groups
- 97% of commercial code uses open source codes - susceptible to attack
- development -   manufacturing - distribution - maintenance - processes - contributors - open source libraries -
- ML extends vuls with pretrained models  and training data suplied by thrid parties
- e.g - chatGPT shutdoun due to open source library - redis-py
> regular monitoring, updates, patches to address new vuls and evolving threats


### 6. Sensitive Information disclosure
> establish terms of use policies,
> informing users about data processing
> providing opt-out options
> "two way trust boundary"
- incomplete filetring might generate biased content generation, may leak data lead to regulatory violation
> robust data sanitization
> strong input validation
> adhering to the priviple of least privilege during model fine tuning
> e.g chatGPT shutdown due to inccorect titling of personal data
> cyberhaven study - 4.7% of workers have entered confidential info into chatgpt
> module training must include the belo
  1.  implement data sanitization
  2.  create strict user policies
  3.  flag PII



### 7. Insecure plugin design
- Plugins act as connectors between llm mdoels/chatgpt to thrid pary applications
- risks of promt engg attacks (inject malicios commands or code into plugins)
- e.g: webPilot plugin
- left shift
> implement least privilege access controls to plugins
> rigorously test plugisn before allwing access to sensitive data
> add a human check for intentional behaviours
> implement encr, access controls, and data
> secure coding pratcices, patching

### 8. Excessive agency


### 9. Over reliance


### 10. Model theft


