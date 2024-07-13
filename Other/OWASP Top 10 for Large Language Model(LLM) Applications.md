# OWASP Top 10 for Large Language Model(LLM) Applications   - from Linkedin Learning

Note: released on Aug 2023

Completion certificate link : https://www.linkedin.com/learning/certificates/8c798e241791bab9e0c96a0063f0fa1b9fff2cdb9de6a27a4e2c8b4cc63b9a05

PMI - https://www.linkedin.com/learning/certificates/7c9812ddb90ef2a22a772390768582b2fa0f7342a1bf54ccfa65c1ff499efc59


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
- incomplete filterring might generate biased content generation, may leak data lead to regulatory violation
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
- developers grant a certain level of control or agency to the model
- agency with excessive privileges to make decisions and take actions - that may go beyong the scope
- this vul may lead to harmful actions such as malfuncstions, prompt injection attacks, malicious plugins, poorly constructed prompts or poor model performance - affects CIA
- e.g:
  - excessive functionality beyond what it is intended to do (plugin inted to read documents may have the ability to modify or edit the documents) - leads to integrity issues
  - excessive permisisons - plugin may have access to other systems beyond the scope defined
  - excessive autonomy - may fail to verify high impr0ved actions independantly - eg. a plugin which allows document deletion, might porceed without even getting the confirmation
- vul can be explited leading to plugin chaining - e.g a plgin for chatgpt to read emails have email send permissions
> excessive functionality - us a plugin  with mail reading capabilities only
> excessive permissions - require user authentication for the user's email service with a read-only scope
> excessive autonomy - requrie manual review and approval  for every email drafted by the LLM plugin or implementing "rate limitting" of the sending interface
> limiting functionalities and coninuously monitoring for the anamolies
> train developers for secure code pratices


### 9. Overreliance
- trust but verify in all situations
- cold war by ronald reagon - trust but through verification process
- malicious actors may exploit them - so dont over rely on any llm
- llms can generate facually incorrect, inappropriate or unsafe,  - refrred to as hallucination or confabulation
> rigorous review process needed
> meahcnism to perfom continuous validation
> establish clear guidelines and train employees to verify outputs
> regularly update and monitor models for any unusual behavious
> ensure legal compliance
> prioritize providng transparency thru disclaimers


### 10. Model theft
- physically stolen, copied or weights and paramenters are extracted to create a functionally equivalent
- caused by weak security controls in your env, leading to unathorized access by APT
- impact - loss of intellctual property, economic and brand damange, competitive disadvantage, unathorized usuage of model, unauthorized access to sensitive information contained within these models
- theft scenarios
  1. insider threats
  2. explpoitation of unknown vuls, misconfigs
  3. shadow model - attacker might craft inputs , - may queirt the model API and prompt injection techniques to gather enought outputs to create a shadow model
> implement access controls
> leverage encr
> develop proper security configuration
> coninuous monitoring



**Test questions: Answered**
1. How does excessive permission pose a possible threat?
- It may give an LLM agent access to other systems beyond what it needs.

2. Why are well-crafted prompts crucial when interacting with an LLM?
- They help to generate the desired result.

3. You are a developer manager for a software company that has recently started to use an LLM for some of the company's production flow. How should you attempt to prevent overreliance?
- Train employees to verify all LLM output.

4. As an LLM developer, how should you protect against injection attacks?
- Validate all prompts.

5. Luca is the head developer of a company that has developed a proprietary LLM. How should he and his team guard against the theft of the model?
- Implement access controls.

6. Why is a data-labeling step critical when building and deploying LLMs?
- It allows the LLM to learn more effectively during the training step.

7. An LLM developer is considering using crowd-sourced data sets to train their LLM. From a training data poisoning perspective, why is this approach risky?
- The data could have been purposely manipulated.

8. You are a developer for a new LLM project. How should you and your team safeguard against Model Denial of Service (MDoS) attacks?
- Limit input/output sizes.

9. A significant weakness in LLMs includes incomplete filtering. Why is this a concern?
- It can lead to inappropriate content generation.

10. Esmeralda needs to have one of her company's applications use a plugin to access ChatGPT. How should she proceed?
- Test the plugin before allowing access to sensitive data.



