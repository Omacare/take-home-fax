# Fax Classification Take Home

## **Objective**

Build a script that **processes and classifies fax emails** using an **AI model**. The system should:

1. Identify "fax" emails from a **mock dataset**.
2. Extract the attached fax file (a text file).
3. Use an AI model to classify the fax into one of three categories:
    - **Patient Referrals**
    - **Prior Authorization Responses**
    - **Patient Records**
4. Store the fax in the correct folder based on classification.
5. Print a notification indicating the classification result.

---

## **Requirements**

- Read from a **mock dataset** (`test_dataset/` folder).
- Identify faxes based on a **predefined sender email pattern**.
- Use **GPT-4o-Mini** to classify the faxes.
- Save each fax into the correct folder:
  - `classified_faxes/patient_referrals/`
  - `classified_faxes/prior_authorizations/`
  - `classified_faxes/patient_records/`
- Simulate sending a notification by **printing a message**.

---

## **Instructions**

### **1. Detect Fax Emails**

- Emails are stored as `.txt` files in the `test_dataset/emails/` directory.
- Each email contains:

    ```
    From: fax@example.com
    Subject: New Fax
    Attachment: fax_001.txt
    
    ```

- Identify emails where `From:` contains `fax@example.com`.

### **2. Extract Attachment**

- The "attachment" is a **text-based file** (e.g., `fax_001.txt`).
- Read the content of the file for classification.

### **3. Classify the Fax Using AI**

- Use **GPT-4o-Mini** via OpenAI’s API. An API_KEY should have been provided to you via a 1Password link along with the link to this repo.
- Example input to the model:

    ```
    "Patient John Doe has been referred to Dr. Smith at XYZ Hospital."
    
    ```

- The model should return a classification:

    ```
    "Patient Referral"
    
    ```

### **4. Store Faxes in Categorized Folders**

- Save the fax in the correct folder under `classified_faxes/`, renaming it with a timestamp:

    ```
    classified_faxes/patient_referrals/fax_20250306_153000.txt
    
    ```

### **5. Send Notification (Simulation)**

- Print a message indicating classification:

    ```
    New fax classified as "Patient Referral" and saved in:
    classified_faxes/patient_referrals/fax_20250306_153000.txt
    
    ```

---

## **Test Dataset**

A **mock dataset** is provided in `test_dataset/` with sample emails and faxes.

### **Folder Structure**

```
test_dataset/
│── emails/
│   ├── email_001.txt
│   ├── email_002.txt
│   ├── email_003.txt
│── faxes/
│   ├── fax_001.txt
│   ├── fax_002.txt
│   ├── fax_003.txt

```

### **Example Data**

### **Example: `email_001.txt`**

```
From: fax@example.com
Subject: New Fax Received
Attachment: fax_001.txt

```

### **Example: `fax_001.txt`** (Patient Referral)

```
Patient Name: John Doe
Referring Physician: Dr. Smith
Referred to: XYZ Hospital
Diagnosis: Severe Hypertension
Notes: Please schedule an appointment for further evaluation.

```

---

## **Deliverables**

- A **Python script** (or another language) that:
  - Reads mock emails
  - Extracts attachments
  - Uses GPT-4o-Mini for classification
  - Stores the file in the appropriate folder
  - Prints a notification
- A **README.md** explaining how the script works.

---

## **Submission Instructions**

1. **Create a GitHub Repository** for your project.
2. **Include the following in your repo**:
    - Your **Python script**.
    - The provided **test dataset**

        []()

    - A **README.md** with setup and usage instructions.
3. **Push your code to GitHub**.
4. **Send a link to your GitHub repository** to [**james@omacare.com**](mailto:james@omacare.com) with the subject:

    ```
    [Intern Take-Home] Your Name - AI Fax Classification Assignment
    
    ```

---

## **Evaluation Criteria**

- **Correctness**: Does the script correctly detect faxes and classify them?
- **AI Integration**: Is GPT-4o-Mini used effectively for classification?
- **Code Readability**: Is the code well-structured and maintainable?
- **Efficiency**: Does the script process multiple emails efficiently?
- **Fallback Handling**: How well does the system handle uncertain classifications?
