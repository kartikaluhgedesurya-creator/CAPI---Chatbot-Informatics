# ISO/IEC 25010 Quality Questionnaire — CAPI

Replication package instrument for:
*Evaluating a Retrieval-Augmented LLM Chatbot for Academic Consultation:
Configuration, Correctness, and Quality-in-Use*

---

## 1. Purpose

This instrument measures users' **perceived** quality of the deployed CAPI
configuration (LLM+RAG+PA, Top-1). It operationalises nine quality aspects drawn
from the ISO/IEC 25010 **Quality in Use** and **Product Quality** models.

The instrument measures perception, not observed behaviour or objective response
correctness. Response correctness was evaluated separately (see the human and
automatic evaluation protocols).

## 2. Administration

| | |
|---|---|
| Delivery | Google Form (self-administered, online) |
| Language | Indonesian |
| Population | Beta-testing participants who had used CAPI |
| Invited | 232 |
| Completed | 231 (one response incomplete, excluded from analysis) |
| Participation | Voluntary, with informed consent |
| Identifiable data | None collected |

## 3. Response scale

All items use the same five-point Likert-type scale:

| Value | Indonesian (as administered) | English |
|---|---|---|
| 1 | Sangat tidak setuju / sangat tidak sesuai | Strongly disagree / not at all |
| 2 | Tidak setuju / tidak sesuai | Disagree |
| 3 | Netral | Neutral |
| 4 | Setuju / sesuai | Agree |
| 5 | Sangat setuju / sangat sesuai | Strongly agree / completely |

Higher values indicate more positive perception. No items are reverse-coded.

## 4. Items

Fifteen items across nine aspects. Item codes match the column names in the
response data file.

### Quality in Use aspects

| Code | Aspect | Item (English translation) |
|---|---|---|
| EFF1 | Effectiveness | You can obtain the information about the Informatics Study Program that you need using CAPI without difficulty. |
| EFI1 | Efficiency | CAPI is able to provide answers quickly and without wasting time. |
| EFI2 | Efficiency | You feel that using CAPI makes it easier for you to get information compared to other methods (such as Google or the website). |
| SAT1 | Satisfaction | CAPI meets your expectations. |
| SAT2 | Satisfaction | You would recommend CAPI to others. |
| FFR1 | Freedom from Risk | You feel that CAPI does not have risks. |
| CTX1 | Context Coverage | CAPI is able to provide relevant answers to various topics related to the Informatics Study Program. |
| CTX2 | Context Coverage | To what extent do you feel CAPI can understand the intent of your questions, even when expressed in different styles or contexts? |

### Product Quality aspects

| Code | Aspect | Item (English translation) |
|---|---|---|
| REL1 | Reliability | CAPI can be used without frequently experiencing disturbances or errors. |
| REL2 | Reliability | CAPI responds quickly when you use it. |
| SEC1 | Security | You feel that your personal data is protected when using CAPI. |
| SEC2 | Security | You feel comfortable providing sensitive information into CAPI. |
| LRN1 | Learnability | How easy is it for you to understand how to use CAPI the first time you try it? |
| ACC1 | Accessibility | You can easily access CAPI through the device you use (such as a smartphone, laptop, or tablet). |
| ACC2 | Accessibility | You can access this chatbot anywhere without any network issues. |

Learnability and Accessibility are sub-characteristics of the ISO/IEC 25010
Product Quality model rather than top-level characteristics. We refer to all
nine collectively as "quality aspects".

## 5. Items per aspect

| Aspect | Items | Codes |
|---|---|---|
| Efficiency | 2 | EFI1, EFI2 |
| Satisfaction | 2 | SAT1, SAT2 |
| Reliability | 2 | REL1, REL2 |
| Security | 2 | SEC1, SEC2 |
| Context Coverage | 2 | CTX1, CTX2 |
| Accessibility | 2 | ACC1, ACC2 |
| Effectiveness | 1 | EFF1 |
| Freedom from Risk | 1 | FFR1 |
| Learnability | 1 | LRN1 |

## 6. Scoring

An aspect score is the mean of its item scores for a respondent. The overall
score is the mean of the nine aspect scores.

Interpretation bands use equal-width intervals of 0.8, derived as (5 − 1) / 5:

| Range | Interpretation |
|---|---|
| 4.20 – 5.00 | Very satisfied |
| 3.40 – 4.19 | Satisfied |
| 2.60 – 3.39 | Neutral |
| 1.80 – 2.59 | Dissatisfied |
| 1.00 – 1.79 | Very dissatisfied |

## 7. Known limitations

These limitations are also discussed in the paper's threats to validity.

**Few items per aspect.** Six aspects use two items; three use one. Cronbach's
alpha for the two-item aspects ranged from 0.565 to 0.667, below the
conventional 0.70 threshold. Alpha is undefined for single-item aspects. Alpha
increases with item count, so low values are expected for two-item scales, but
per-aspect scores should be read as indicative rather than definitive.

**Self-report.** All items capture perception. They do not measure observed use,
task success, or response correctness.

---
