# CV Build Test for a New Project  

## Objective  
This project aims to build the CV for a new project.  

### **Input & Output**  
- **Input CV:** [PCMDI/input4MIPs_CVs](https://github.com/PCMDI/input4MIPs_CVs/tree/main/CVs)  
- **Output:** A repository compatible with the ESGVOC library: [ESGF Vocabulary](https://esgf.github.io/esgf-vocab/)  

---

## **Project Steps & Progress**  

### **1. Repository Setup**  
- Create a new repository or a branch within an existing one to store the new project CV format (this repository).  

### **2. Define the DRS (Directory, Filename, Dataset Name)**  
- Most projects have a **DRS** linked to the CV.  
- Define the DRS in the correct format.  
- Example: [CMIP6Plus Project Specs](https://github.com/WCRP-CMIP/CMIP6Plus_CVs/blob/esgvoc/project_specs.json).  

**Tracking history:**  
- A simple script (`scripts/build_drs.py`) will be used to track the history of each file.  
- This script is project-specific (not reusable) and was written for efficiency.  
- **Output:** `project_spec.json` is created!  

---

### **3. Create Directories for Each Collection**  
Each collection requires a directory containing **terms** and **context** files.  

#### **Example: "activity" Collection**  
- Source: [input4MIPs_activity_id.json](https://github.com/PCMDI/input4MIPs_CVs/blob/main/CVs/input4MIPs_activity_id.json).  
- It contains only one term: **input4MIPs**.  

#### **Checking CMIP Universe Compatibility**  
- Verify if the term exists in the **CMIP Universe**:  
  [WCRP-Universe Activity](https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc/activity)  
- **Result:** **Not found**.  

#### **Two Solutions**  
1. **Request Addition:** Open an issue in the **WCRP-Universe repository**.  
2. **Create a New Term** (not covered here).  

Once the term is added to the WCRP-Universe repository, proceed with the following steps:  

#### **Steps to Integrate in This Repository**  
1. **Create a directory** → `input4MIPs_activity_id/`  
2. **Add a context file** → `000_context.jsonld`  
   - Use an existing template:  
     [Example Context File](https://github.com/WCRP-CMIP/CMIP6Plus_CVs/blob/esgvoc/activity_id/000_context.jsonld).  
3. **Add the term definition** → `input4MIPs.json`  
   - Fetch relevant data from the **CMIP Universe**.  
   - Use an existing example:  
     [Example Term File](https://github.com/WCRP-CMIP/CMIP6Plus_CVs/blob/esgvoc/activity_id/cmip.json).  
   - Modify the ID to match the universe's ID.  

---

### **Repeat for Each Collection & Required Terms**  
Follow the above steps for all necessary collections and terms. 


#### institution_id 

institution is a known datadescriptor in the universe. 
##### Create context

lets take the institution context and copy/paste it in a input4MIPs_institution_id directory  

##### Create terms

then, for each term, check if it exists in universe, if not : ask for it the be registered 

for now those are missing : 
CR not found in universe
DRES not found in universe
UCLA not found in universe
uoexeter not found in universe
+ 
CNRM-Cerfacs is CNRM-CERFACS in universe 

lets put that aside for now 

## esgvoc 

the idea is to define a new configuration with this repo as a new project (in version 3.0.0) the configuration is only available through code, lets create a script for that:







That’s all, folks! 🚀
