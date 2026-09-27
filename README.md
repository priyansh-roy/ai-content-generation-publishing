# AI Content Generation & Multi-Platform Publishing Engine

An AI-powered content operations and social media publishing workflow built and deployed during my AI Automation Internship at Caremeez.

---

## 📌 Project Snapshot

| | |
|---|---|
| **Organization** | Caremeez |
| **Role** | AI Automation Intern |
| **Project Type** | AI Content Operations & Social Media Automation |
| **Timeline** | October 2025 |
| **Platforms** | LinkedIn & Facebook |
| **Core Tools** | n8n, OpenAI, Google Sheets, LinkedIn API, Facebook Graph API |
| **Deployment Status** | Successfully built, tested and used for live publishing; later paused due to Facebook authentication dependency |
| **Live Output** | 10–15 successfully published posts |

---

## 🎯 Overview

During my AI Automation Internship at Caremeez, I worked on automating the company's healthcare content publishing process.

The existing process relied on recurring manual effort for preparing and publishing healthcare-related content. Maintaining a consistent publishing process required manual effort, and there was no structured system that could take a healthcare topic, turn it into a publish-ready post, distribute it across platforms, and maintain a record of what had already been published.

I designed and built an end-to-end automation in n8n that automated this process.

The workflow could generate a fresh healthcare topic using AI, check it against previously used topics, generate the corresponding healthcare awareness post, publish it automatically to Caremeez's LinkedIn and Facebook Pages, and maintain the generated content and publishing status in Google Sheets.

The workflow was designed to run on a configurable schedule, allowing the process to operate without manual intervention once it had been configured and tested.

---

## 💡 Business Problem

Caremeez was manually handling its social media publishing process.

The main challenges were:

- Maintaining consistent publishing required recurring manual effort.
- There was no structured pipeline for content ideation, generation, publishing and tracking.
- Previously used topics could be repeated.
- Content history and publishing status needed centralized tracking.

The objective was to create a repeatable system that could move from:

**Content Ideation → Content Generation → Publishing → Tracking**

---

## 🎯 Project Objectives

The automation was designed to:

- Automatically generate fresh healthcare-related topics.
- Prevent previously used topics from being generated again.
- Generate relevant healthcare awareness content.
- Maintain a record of generated topics and content.
- Automatically publish content to LinkedIn and Facebook.
- Track the publishing status of generated content.
- Run according to a configurable schedule.
- Eliminate routine manual involvement after setup and testing.

---

## ⚙️ Solution

I designed the automation as an end-to-end content operations pipeline rather than automating only the final posting step.

### High-Level Workflow

**Scheduled Trigger → AI Healthcare Topic Generation → Retrieve Existing Topics → Duplicate Topic Check → AI Content Generation → Google Sheets Logging → LinkedIn + Facebook Publishing → Publishing Status Update**

Google Sheets acted as the workflow's lightweight content-tracking layer, storing previously generated topics, generated content and publishing status.

---

## 🔄 Automation Flow

### 1. Scheduled Trigger

The workflow starts through a scheduled trigger, allowing the publishing frequency to be configured instead of manually initiating each content-generation cycle.

### 2. AI Healthcare Topic Generation

The first AI stage generates a fresh healthcare-related topic.

The topic-generation logic focused on content that was:

- Relevant to healthcare
- Current or trend-connected
- Relatable to an Indian audience
- Relevant to everyday life
- Suitable for awareness-oriented social media content
- Written in a natural tone

### 3. Duplicate Topic Detection

Previously generated topics are retrieved from Google Sheets.

The workflow checks the newly generated topic against the existing topic history.

If a duplicate is detected, the workflow generates another topic instead of continuing with the duplicate.

### 4. AI Content Generation

Once a unique topic is available, the workflow generates the corresponding healthcare awareness post.

The generated content follows the defined content requirements and is prepared for social media publishing.

### 5. Google Sheets Tracking

The generated topic and content are recorded in Google Sheets.

The sheet also maintains the publishing status of the generated content.

### 6. Multi-Platform Publishing

After the content is generated and recorded, the workflow automatically publishes the post to:

- Caremeez LinkedIn Organization Page
- Caremeez Facebook Page

The workflow uses the respective platform APIs rather than requiring manual copy-pasting.

### 7. Publishing Status Update

After the publishing stage, the workflow updates the corresponding record in Google Sheets with the publishing status.

---

## 🏗️ Technical Architecture

| Component | Purpose |
|---|---|
| **n8n** | Workflow orchestration and execution |
| **OpenAI** | Healthcare topic ideation and social content generation |
| **Google Sheets** | Content history, topic tracking and publishing status |
| **LinkedIn API** | Organization-page publishing |
| **Facebook Graph API** | Facebook Page publishing |
| **Scheduled Trigger** | Automated workflow execution |

The main engineering focus was connecting these components into a repeatable content pipeline rather than treating each task as an isolated automation.

---

## 👨‍💻 My Role

I independently handled the design and implementation of the automation.

My responsibilities included:

- Understanding the content publishing problem
- Designing the end-to-end workflow architecture
- Building the workflow in n8n
- Designing AI prompts for topic and content generation
- Implementing duplicate-topic detection
- Integrating Google Sheets
- Integrating the LinkedIn API
- Integrating the Facebook Graph API
- Configuring credentials and permissions
- Testing the workflow with live platforms
- Troubleshooting API and authentication issues
- Verifying successful live publishing

Caremeez provided the required company credentials and platform access where necessary. The workflow design, implementation, AI logic and API integration were handled by me.

---

## 📈 Results

The automation was successfully tested with approximately **10–15 live posts**.

The system demonstrated that the complete process could be automated from topic generation to multi-platform publishing.

### Before

Manual topic/content process → Manual refinement → Manual publishing → Recurring effort

### After

Scheduled execution → AI topic generation → Duplicate prevention → AI content generation → Automatic LinkedIn + Facebook publishing → Centralized status tracking

Once configured and tested, the normal publishing process required **zero routine manual involvement**.

---

## 📸 Project Evidence

### n8n Workflow

![n8n Workflow](assets/workflow.png)

### LinkedIn Live Output

![LinkedIn Output](assets/linkedin-output.png)

### Facebook Live Output

![Facebook Output](assets/facebook-output.png)

### Google Sheets Tracking

![Google Sheets Tracking](assets/google-sheets-tracking.png)

---

## ⚠️ Deployment Challenge

The primary deployment challenge was related to **Facebook Page authentication and access-token management**.

The required Page-level credentials were not consistently available, which eventually prevented continued operation of the Facebook publishing component.

The automation itself was successfully built and tested, but the Facebook publishing component could not continue operating reliably because of the external authentication dependency.

This highlighted an important practical aspect of automation deployment:

> A technically complete workflow can still depend on external platform permissions, credentials and authentication lifecycle management.

---

## 🧠 Engineering Learnings

### 1. Automate the workflow, not just the task

The project connected:

**Ideation → Validation → Generation → Publishing → Tracking**

rather than automating only the final posting step.

### 2. AI needs system-level controls

AI generation alone does not guarantee useful or non-repetitive output.

The workflow added structured prompts, topic constraints, duplicate detection and output requirements around the AI model.

### 3. External APIs are part of the engineering problem

Authentication, permissions, access tokens and platform-specific requirements can directly affect whether an automation remains operational in production.

### 4. Automation does not always mean removing humans

The architecture can also support a human approval step before publication if editorial control is required.

---

## ♻️ Reusable Components

The project produced reusable components including:

- Scheduled content generation
- AI topic ideation
- Duplicate-topic prevention
- Structured AI content generation
- Google Sheets-based content tracking
- Multi-platform publishing
- Publishing-status tracking
- Optional human approval layer
- API-based social media integration

---

## 📌 Project Status

**Successfully built, tested and used for live publishing.**

The project was later paused because of the Facebook Page authentication/access-token dependency, which prevented continued operation of the Facebook publishing component.

---

## 🌐 Portfolio

For the complete case study and additional automation projects:

**[View My Portfolio](https://priyansh-roy.github.io/priyansh-portfolio/)**

---

## 🛠️ Tech Stack

`n8n` · `OpenAI` · `Google Sheets` · `LinkedIn API` · `Facebook Graph API`
