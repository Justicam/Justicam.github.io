---
layout: project
type: project
image: img/audit_image.jpg
title: "Cyber Security Portfolio: Security Audit"
date: 2026
published: true
labels:
  - Security Audit
summary: I conducted a security audit.
---

**This scenario is based on a fictional company:**

Botium Toys is a small U.S. business that develops and sells toys. The business has a single physical location, which serves as their main office, a storefront, and warehouse for their products. However, Botium Toy’s online presence has grown, attracting customers in the U.S. and abroad. As a result, their information technology (IT) department is under increasing pressure to support their online market worldwide. 

The manager of the IT department has decided that an internal IT audit needs to be conducted. She's worried about maintaining compliance and business operations as the company grows without a clear plan. She believes an internal audit can help better secure the company’s infrastructure and help them identify and mitigate potential risks, threats, or vulnerabilities to critical assets. The manager is also interested in ensuring that they comply with regulations related to internally processing and accepting online payments and conducting business in the European Union (E.U.).   

The IT manager starts by implementing the National Institute of Standards and Technology Cybersecurity Framework (NIST CSF), establishing an audit scope and goals, listing assets currently managed by the IT department, and completing a risk assessment. The goal of the audit is to provide an overview of the risks and/or fines that the company might experience due to the current state of their security posture.

My task is to review the IT manager’s scope, goals, and risk assessment report. Then, perform an internal audit by completing a controls and compliance checklist. 

**Supporting Materials:**

• [Scope, goals, and risk assessment report](https://docs.google.com/document/d/1s2u_RuhRAI40JSh-eZHvaFsV1ZMxcNSWXifHDTOsgFc/template/preview)

• [Control categories](https://docs.google.com/document/d/1HsIw5HNDbRXzW7pmhPLsK06B7HF-KMifENO_TlccbSU/template/preview)

**My Audit**

• [Controls and compliance checklist](https://docs.google.com/document/d/1jbhPUl06JFw1uKgUpW7ZsqroAGTAf4LpdqOnoKPDy-g/edit)

**Recommendations**

Botium Toys has a risk scored an 8 on a scale of 1 to 10. The physical security is noted as sufficient, which is positive. The focus must now shift to cybersecurity and data governance. The single most dangerous flaw is all employees having potential access to unencrypted cardholder data. Fixing that, along with access controls and backups, will address the most existential threats to the company. Consider engaging a third-party security consultant to assist with the technical implementation and compliance assessment.

| Priority        | Area                   | Key Actions                                                                                                                                       |
| :-------------- | :--------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------ |
| **CRITICAL**    | **Data Protection**    | • Network segmentation for sensitive data<br>• Implement encryption for cardholder data (at rest & in transit)<br>• Isolate PII/SPII to restricted access zones |
| **CRITICAL**    | **Access Control**     | • Implement Least Privilege principle<br>• Deploy Role-Based Access Control (RBAC)<br>• Establish separation of duties for critical functions      |
| **CRITICAL**    | **Business Continuity**| • Establish 3-2-1 backup strategy (encrypted, offsite)<br>• Create basic disaster recovery plan<br>• Test restoration procedures immediately      |
| **HIGH**        | **Credential Security**| • Update password policy (12+ chars, complexity)<br>• Implement enterprise password manager<br>• Eliminate shared/default credentials              |
| **HIGH**        | **Threat Detection**   | • Deploy IDS/IPS at network boundaries<br>• Focus monitoring on sensitive data segments<br>• Establish baseline for normal traffic patterns        |
| **MEDIUM**      | **Process & Compliance**| • Formalize patch management schedule<br>• Develop comprehensive Incident Response Plan<br>• Align with PCI DSS and GDPR requirements             |
| **FOUNDATIONAL**| **Security Culture**   | • Mandatory security awareness training<br>• Regular phishing simulations<br>• Role-specific data handling procedures                              |




