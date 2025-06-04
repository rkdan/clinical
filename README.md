# Reformatting patient presentations with LLMs
Following some changes to the clinical school's Learning Management System (LMS) some resources needed to be reinstated, one of which was a collection of pages intended to help students structure their approach to common clinical scenarios, such as 'chest pain', abdominal mass' etc. - common symptoms that patients present with to a medical professional.

This content allows students to think in terms of symptoms, not just diagnoses, which reflects how patients actually present in real life.

These Patient Presentation pages were written by medical professionals, and the eLearning team was tasked with incoporating them into a digital resource that is accessible and conducive for student learning.

There are 176 different patient presentations, divided into sections, where specific information is given in regard to the stage fo care and demographic:
- Primary care
- Secondary care
- Paediatric context
- Geriatric context.

Here is an example of a patient presentation page:

### Primary care context
Identifying an underlying cause in patients who have difficulty communicating, those at the extremes of age and in pregnancy requires careful practice and skill, and the recent shift to remote consultation has exacerbated this. Consider elements of the narrative, examination and risk assessment that would suggest the acute abdomen requiring urgent surgical or gynaecological assessment and ambulance transfer from home or the surgery. Be aware of common causes such as infantile colic, constipation, gastroenteritis, and dysmenorrhoea that may be possible to manage conservatively, and when atypical presentations would prompt concern. Speak to the GP tutor about how they approach abdominal pain, who they bring to the surgery for review and what symptoms or signs would prompt further investigation. Discuss the options- which blood tests are appropriate, and what is their sensitivity/specificity like? Who would you check urine and blood glucose in? Review the local 2-week wait criteria, and consider which patients merit an endoscopy, urgent direct access CT or USS. Abdominal pain is a very common symptom in children and young people- be aware of features that may suggest malignancy, or surgical emergencies such as appendicitis. Get familiar with using a patient's electronic records to identify possible contributing factors to their presentation, such as medication and conditions such as diverticular disease or aneurysms.

### Secondary care context
Abdominal pain is one of the most common presenting symptoms in healthcare – especially in A&E. Its time-course can be acute, subacute or chronic, and can vary in severity – from benign to life-threatening, affecting all age ranges. One example you may see is a 10-year-old child in the paediatric assessment unit with subacute abdominal pain in the umbilical region for 5 days followed by localisation to the right iliac fossa with fevers and reduced oral intake. Another example is that of a 20-year-old sexually active female who is not on contraception, has missed her last two periods and has now presented with acute abdominal pain and per-vaginal bleeding to A&E. A final example may be an elderly gentleman who is an inpatient on a geriatric ward. He takes opioid analgesia for his lower back pain and has not passed stools for several days but continues to pass wind - his per-rectal exam shows impacted stools. A useful starting point with assessing any patient presenting with abdominal pain is whether the patient is haemodynamically unstable or not, as the former will indicate a life-threatening differential and will determine the urgency of any relevant investigations and interventions. A systematic history taking for such a patient would include characterisation of the pain (SOCRATES) as well as a systemic screen e.g. fevers, night sweats, weight loss – being aware that an O&G history is vital for any female patient. Examination would include an abdominal and PR exams +/- cardiorespiratory exam +/- gynaecological exam. Initial investigations may include a urine pregnancy test (mandatory in females of child-bearing age), urinalysis +/- MCS, blood tests including group & screen +/- crossmatch, AXR (if suspecting bowel obstruction) and US/CT imaging. Further investigations can include endoscopy or diagnostic laparoscopy. There are a myriad of differentials to consider for abdominal pain and a careful synthesis of history, examination and investigation is required to refine your differential and to enact focused management.

### Paediatric care context
Abdominal pain is one of the most frequent complaints in children presenting in primary or secondary care. Common causes for abdominal pain include viral gastroenteritis or constipation. Children also commonly present with functional abdominal pain. However, the differential diagnosis includes multiple organic causes that need to be considered through a thorough history and examination. Try to think about red flags (for example bloody stool, acute onset, localized or night time pain) that help identify those cases that need urgent attention and/or intervention.

### Geriatric care context
Again, the usual differentials apply, but commonly seen causes include: constipation, ileus, IBS, hypercalcaemia, ischaemic bowel, diverticular disease and late onset coeliac disease. It is important to distinguish between acute vs chronic vs acute on chronic pain.

## The Issue
These pages were sampled by a group of students before being released to the wider cohort, as well as being reviewed by colleagues.

From that additional feedback, the team were hearing requests for the content in these patient presentations to be formatted differently, in a more readable and digestible way. The original content was written in a way that was not conducive to digital learning, with long paragraphs and no clear structure. The eLearning team wanted to reformat the content to make it more accessible and easier to navigate for students.

## Old Worflow
For a given presentation, the team would:
1. Copy each care context section into ChatGPT
2. Ask ChatGPT to reformat the content into a more readable and digestible format, with clear headings and bullet points
3. Copy the reformatted content back into the LMS

The team iterated over a few prompts to get the desired output, but it was still a manual process that took a lot of time - a total of 9 copy and paste actions per presentation!

Overall, this process took approximately 3 days to complete for all 176 presentations.

## New Example Workflow
All data exists in an Airtable, which can be exported to a `.csv` file. This `.csv` file can be easily loaded and accessed programmatically, using the `pandas` library in Python.

The new workflow consists of 3 phases:

1. Access and reformat data
2. Reformat the care context sections using an LLM
3. Validate reformatted content

This third step is an important component that was missing from our original workflow. This process would involve a human reading and reviewing the reformatted content to ensure that it matches the original content exactly. This is essential for maintaining the integrity of the educational material. However, this step is very time consuming.

1. Load the `.csv` file into a pandas DataFrame
2. Combine the care context sections into a single string and store it in a new dataframe column in order to preserve the original

Ensuring each care context is extracted.
