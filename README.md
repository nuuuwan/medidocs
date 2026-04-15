# medidocs

![Status](https://img.shields.io/badge/status-pre--alpha-green) ![License](https://img.shields.io/badge/license-MIT-lightgrey)

> An open, AI-assisted platform for persistent, party-independent medical documentation in Sri Lanka — and beyond.

---

## The problem

Medical records in Sri Lanka live in fragments. A patient's consultation notes may be handwritten in a clinic file, their lab results issued as a paper printout, and their hospital discharge summary filed in a ward register — with no reliable link between them. When a patient changes doctor, visits a specialist, or is admitted in an emergency, critical history is routinely unavailable.

This is not merely an inconvenience. It duplicates diagnostic effort, delays treatment, and places the burden of recall on the patient or their family. No single institution or government system currently owns this problem. **medidocs** is a proposal for infrastructure that fills that gap.

> Sri Lanka has no national electronic health record system. This project treats that absence not as a blocker but as an opportunity to design something fit for purpose from the ground up.

---

## Design principles

### Party independent

Documentation can be initiated by the patient, a treating doctor, a caregiver, a hospital ward, or any authorised third party. No single actor owns the record.

### Minimal input friction

AI-assisted capture is the default. OCR for scanned results and printed forms, ASR for spoken consultation notes, and structured extraction from free text reduce manual data entry to a last resort.

### Flexible data model

No two medical episodes are alike. The document schema is designed to accommodate consultations, test results, prescriptions, imaging reports, hospital stays, and document types not yet anticipated.

### Patient-sovereign

The patient (or their designated proxy) holds the canonical access grant. Institutions contribute to the record but do not own it.

---

## High-level architecture

medidocs is conceived as a layered system. Each layer is independently useful and can be adopted incrementally.

**Layer 1 — Capture**
Multi-modal ingestion via OCR, ASR, photo upload, structured form entry, and direct EHR integration where available. Designed for low-bandwidth and mobile-first contexts.

**Layer 2 — Normalisation**
AI-assisted extraction and mapping of raw inputs into a canonical flexible document model. Handles Sinhala, Tamil, and English source material.

**Layer 3 — Storage**
Encrypted, versioned record store. Document provenance — who created what, when, and in what role — is preserved immutably.

**Layer 4 — Access & consent**
Fine-grained access control. Patients grant, audit, and revoke access. Clinicians request access with documented purpose. Emergency override protocols are explicit and logged.

**Layer 5 — Presentation**
A timeline-first view of the patient record, readable by both clinicians and patients. Summaries can be generated in plain language on demand.

---

## Document model

The core model treats every medical event as a *document* with a small set of required fields — patient identifier, timestamp, author, document type — and an open-schema payload that varies by type. Document types are extensible. The initial set includes:

- Consultation note
- Lab result
- Imaging report
- Prescription
- Hospital admission
- Discharge summary
- Surgical record
- Vaccination record
- Patient-reported event
- Referral letter

---

## Who is this for?

**Patients and caregivers** who want a single, portable, longitudinal view of a health history. **Clinicians** who need reliable prior history at the point of care. **Hospitals and clinics** that want to offer better continuity without building proprietary infrastructure. **Developers and researchers** interested in building on an open medical records layer for Sri Lanka.

---

## Status

medidocs is currently in the design and early prototyping phase. This repository contains the conceptual specification, data model proposals, and an initial API sketch. Contributions, critiques, and domain expertise — especially from the Sri Lankan healthcare community — are actively welcomed.

---

## Contributing

See `CONTRIBUTING.md`. If you are a clinician, health administrator, or policy person rather than a developer, your input is equally valuable — open an issue or start a discussion.

---

*medidocs is an open initiative. It is not affiliated with the Ministry of Health Sri Lanka or any private healthcare provider. Nothing in this repository constitutes medical advice.*
