---
layout: default
title: FAQs
parent: § Definition of Critical Software Under Executive Order (EO) 14028 
grand_parent: NIST 
nav_order: 50 
---
<style>
.dont-break-out {
  /* These are technically the same, but use both */
  overflow-wrap: break-word;
  word-wrap: break-word;

     -ms-word-break: break-all;
  /* This is the dangerous one in WebKit, as it breaks things wherever */
  word-break: break-all;
  /* Instead use this non-standard one: */
  word-break: break-word;
}

.youtube-container {
    position: relative;
    width: 100%;
    height: 0;
    padding-bottom: 56.25%;
}
.youtube-video {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}

</style>

<div class="dont-break-out" markdown="1">

1. TOC
{:toc}

## FAQs
The following FAQs were compiled in consultation with OMB and CISA to provide additional context to the material.

**1. When will the next phase begin?**  
*CISA and OMB will monitor the implementation of the program in the initial phase and decide when to include additional software categories.*

**2. What do you mean by “direct software dependencies” in the definition?**  
*For a given component or product, we mean other software components (e.g., libraries, packages, modules) that are directly integrated into, and necessary for operation of, the software instance in question. This is not a systems definition of dependencies and does not include the interfaces and services of what are otherwise independent products.*

**3. What do you mean by “critical to trust” in the definition?**  
*“Critical to trust” covers categories of software used for security functions such as network control, endpoint security, and network protection.*

**4. Does it matter if the software product is in the cloud or in an on-premises or a hybrid environment?**   
*No. If a product or service provides functions that are part of the definition of EO-critical, then the product or service itself is EO-critical, regardless of its deployment model. Having said that, NIST has recommended that the initial phase of the EO focus on onpremises software. Many on-premises products rely on cloud-based components and services that perform EO-critical functions (e.g., cloud-based access control). In such situations, the on-premises components are in scope if they directly perform EO-critical functions. It is suggested that cloud-based components and systems be addressed in later phases of implementation to allow time to coordinate with other Federal requirements for such systems (e.g., FedRAMP).*

**5. Can open source software be EO-critical?**  
*Yes. If open source software performs functions that are defined as EO-critical, then it is EO-critical. In practice, open source software is often incorporated into other products. In this case, the product developer will treat the open source components as part of their own development process. In other situations, the open source software is a standalone product. In this case, the requirements of the EO still apply. The Government may need to address some of the requirements under Section 4(e) itself if the open source community supporting the product does not or cannot.*

**6. Can Government-developed software be EO-critical?**  
*Yes. The Federal Government develops software both in-house and through contracts. These products are often referred to as GOTS (government-off-the-shelf) software. If GOTS software performs functions included in the definition of EO-critical, then it is EOcritical. While Section 4 of the EO does not make a distinction between commercial and GOTS software, the manner in which GOTS software is developed and procured may necessitate differences in the standards, procedures, and criteria that will be developed for critical software under this EO.*

**7. What if a product is partly EO-critical and partly not?**  
*If a product contains functions that are part of the definition of EO-critical, then the product itself is EO-critical. However, some EO-critical software products may contain distinct components that do not have EO-critical attributes or do not directly support the EO-critical functions provided by the product. When developers attest to the security measures under Section 4(e), they can specify which components of their product are EOcritical and meet the security measures in 4(e) and which are not. While this may lead vendors to different interpretations for how to scope their attestations, the objective is to require vendors to be clear about which components are being attested to and which are not.*

**8. What if the software is purchased as a component of another product?**  
*If a product performs functions that are part of the definition of EO-critical, then the product itself is EO-critical. When vendors attest to the implementation of the security measures under Section 4(e), they can specify which components of their products are covered. These may include components developed by other parties. For example, if the Government is buying a product that contains an operating system, the product is EOcritical and requires an attestation about the security measures, but the attestation can be limited to the operating system. See FAQ #7.*

**9. How will this work with FedRAMP?**  
Section 3 of the EO addresses modernization of FedRAMP. The recommended phased approach starts with on-premises software, with the understanding that some onpremises software which relies on cloud-hosted components may be in scope. CISA will coordinate with FedRAMP to define the scope and applicability of the EO to cloud-based software in later phases of the implementation.

**10. The definition excludes software that won’t be deployed in production systems for operational purposes. Can you provide more explanation?**  
*There are several use cases where software is owned but is not deployed in a manner that would pose a significant risk of harm if compromised. Examples include software used as the subject of research and software collected for archival purposes. This will allow the Government to purchase software that is EO-critical for these non-operational uses even if the vendor has not implemented or attested to the security measures in 4(e).*

**11. What about software used in National Security Systems (NSS)? Are they covered?**  
*Section 9 of the EO describes the applicability of the requirements of this EO to National Security Systems.*

**12. Can embedded software or firmware be EO-critical?**  
*Yes. If embedded software or firmware performs functions that are defined as EOcritical, then it is EO-critical. Due to the complexities of such products, we recommended that such software not be included in the initial phase of implementation.*

**13. Shouldn’t departments and agencies decide what is EO-critical based on how the software is used to support the agency’s mission?**  
*No. The definition of EO-critical is based on the functions of the software, not its use. This will enable software vendors to know if their products are EO-critical independent of individual acquisitions and deployments, so they can address the requirements of Section 4(e). This will create clarity in the marketplace. Otherwise, the Government might seek to buy a product, but no vendor anticipated it would be EO-critical, resulting in either no products or a limited number of products available for the Government to purchase. The types of software defined by the table are likely to be EO-critical in most situations.*

**14. What about safety-critical or other high-assurance systems?**  
*There are many types of safety-critical and other high-assurance systems. Many of them have regulatory or industry-based security requirements. If these systems make use of software that contains EO-critical functions, then that software is EO-critical. Safetycritical and high-assurance software and systems will have additional security requirements. For example, if a high-assurance system contains an operating system, the operating system is EO-critical and must meet the EO-critical requirements in addition to the safety-critical or other system requirements.*

**15. If I am using a software product that is not included in the EO-critical list, but it is critical for me, can I ask the vendor to provide attestation?**  
*Yes, departments and agencies can leverage the EO-critical security measures defined in Section 4(e) as part of a procurement.*
***

#### Table of Contents
{: .no_toc}

<ul><li> <a href="/docs/nist/Definition-of-Critical-Software-Under-Executive-Order-(EO)-14028-1/">Introduction</a></li><li> <a href="/docs/nist/Definition-of-Critical-Software-Under-Executive-Order-(EO)-14028-2/">Background</a></li><li> <a href="/docs/nist/Definition-of-Critical-Software-Under-Executive-Order-(EO)-14028-3/">Approach</a></li><li> <a href="/docs/nist/Definition-of-Critical-Software-Under-Executive-Order-(EO)-14028-4/">Definition and Explanatory Material</a></li><li> <a href="/docs/nist/Definition-of-Critical-Software-Under-Executive-Order-(EO)-14028-5/">FAQs</a></li></ul>

***

</div>
