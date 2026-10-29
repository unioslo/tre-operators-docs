<section class="tre-hero">
	<div class="tre-hero-main">
		<p class="tre-eyebrow">EOSC-ENTRUST</p>
		<h1>EOSC-ENTRUST Blueprint</h1>
		<p class="tre-lead"> EOSC-ENTRUST is developing a scalable, interoperable framework for secure, federated access to sensitive research data across Europe. The project is aligned with the European Health Data Space (EHDS) and the European Open Science Cloud (EOSC), and it is grounded in real-world implementation needs. The ENTRUST Blueprint defines the minimal requirements for joining a federated TRE ecosystem. It covers:
			
- architecture specifications
- legal templates
- operating procedures
- interface definitions for Authentication, Authorization, and Auditing Infrastructure (AAAI)
			
This guide walks you through these components module by module. A TRE Provider Catalogue complements it by giving researchers a structured overview of available environments and their access and security specifications. Together, these outputs advance cross-border collaboration in sensitive data research. This guide is part of the EOSC-ENTRUST Training Package and helps Trusted Research Environment (TRE) providers build, operate, and maintain secure, compliant, and interoperable environments that are ready to join a federated ecosystem across Europe.</p>

		<div class="tre-hero-actions">
			<a class="tre-hero-link" href="fundamentals/"><i class="fa-solid fa-book-open tre-icon-inline" aria-hidden="true"></i>Start with fundamentals</a>
			<a class="tre-hero-link tre-hero-link-secondary" href="modules/architecture/"><i class="fa-solid fa-diagram-project tre-icon-inline" aria-hidden="true"></i>View architecture</a>
			<a class="tre-hero-link tre-hero-link-secondary" href="federation/"><i class="fa-solid fa-globe tre-icon-inline" aria-hidden="true"></i>Read federation guide</a>
		</div>
	</div>

	<div class="tre-hero-side">
		<div class="tre-hero-panel">
			<h2><i class="fa-solid fa-table-cells-large tre-icon-heading" aria-hidden="true"></i>At a Glance</h2>
			<ul>
				<li><i class="fa-solid fa-layer-group tre-icon-list" aria-hidden="true"></i>6 core modules</li>
				<li><i class="fa-solid fa-list-check tre-icon-list" aria-hidden="true"></i>9 setup steps</li>
				<li><i class="fa-solid fa-shield-halved tre-icon-list" aria-hidden="true"></i>Architecture, interfaces, legal, and operations guidance</li>
			</ul>
		</div>
	</div>
</section>

<div class="tre-summary-grid">
	<article class="tre-summary-card">
		<h2><i class="fa-solid fa-compass tre-icon-heading" aria-hidden="true"></i>Start Here</h2>
		<p>Understand the TRE model, terminology, and core expectations before setup.</p>
		<a href="fundamentals/"><i class="fa-solid fa-arrow-right tre-icon-inline" aria-hidden="true"></i>Open fundamentals</a>
	</article>

	<article class="tre-summary-card">
		<h2><i class="fa-solid fa-server tre-icon-heading" aria-hidden="true"></i>Deploy Core Services</h2>
		<p>Review the architecture, federation dependencies, and trust components.</p>
		<a href="modules/architecture/"><i class="fa-solid fa-arrow-right tre-icon-inline" aria-hidden="true"></i>Open architecture</a>
	</article>

	<article class="tre-summary-card">
		<h2><i class="fa-solid fa-scale-balanced tre-icon-heading" aria-hidden="true"></i>Operate and Govern</h2>
		<p>Use the procedures and legal modules to support onboarding, monitoring, and compliance.</p>
		<a href="modules/procedures/"><i class="fa-solid fa-arrow-right tre-icon-inline" aria-hidden="true"></i>Open procedures</a>
	</article>
</div>

## Learning Objectives

- Understand TRE concepts and terminology
- Set up and configure TRE architecture
- Implement interfaces and operational procedures
- Apply legal and compliance requirements
- Integrate with federated TREs

## Who is this guide for?

- TRE User: Researchers and analysts working with sensitive data -
	- They should access and use an approved TRE workspace safely and in line with training and accreditation requirements. 
 	- <a href="fundamentals/"><i class="fa-solid fa-arrow-right tre-icon-inline" aria-hidden="true"></i>Start with M1: TRE Fundamentals</a>
	</article>
- TRE Operator: The team running a TRE day to day -
	- They should onboard users, monitor the environment, respond to incidents, and manage agreements and compliance.
 	- <a href="modules/procedures/"><i class="fa-solid fa-arrow-right tre-icon-inline" aria-hidden="true"></i>Start with M4: Operating Procedures</a>
	</article>
- TRE builder: The technical team setting up the infrastructure -
	- They should construct infrastructure, deploy core components, install 5S-TES, configure AAAI, implement interfaces, and connect the TRE to the federation. 
 	- <a href="modules/architecture/"><i class="fa-solid fa-arrow-right tre-icon-inline" aria-hidden="true"></i>Start with M2: Architecture</a>
	</article>

## Why this matters?
Researchers who want to share sensitive data across borders face several obstacles:
- Sensitive research data is siloed across national boundaries, with no common framework for secure cross-border federated access.
- GDPR and EHDS impose strict requirements for processing sensitive data, but leave the technical implementation largely undefined.
- TRE providers show low federation readiness, with fragmented architectures and inconsistent terminology.
- There are no standardised procedures for user registration, data access requests, or cross-border legal harmonisation across TREs.

The Blueprint and this guide address these gaps by giving TRE providers a common, practical path to federation readiness.
<div class="tre-card-grid tre-card-grid-steps">

	<article class="tre-card tre-step-card">
		<h3><span class="tre-card-number">1</span><i class="fa-solid fa-book tre-icon-heading" aria-hidden="true"></i>Understand TRE Fundamentals</h3>
		<ul>
			<li>Read <a href="fundamentals/">TRE Fundamentals</a>.</li>
			<li>Review key terminology in the <a href="appendices/glossary/">Glossary</a>.</li>
		</ul>
	</article>

	<article class="tre-card tre-step-card">
		<h3><span class="tre-card-number">2</span><i class="fa-solid fa-sitemap tre-icon-heading" aria-hidden="true"></i>Review Reference Architecture</h3>
		<ul>
			<li>Study <a href="modules/architecture/">Architecture</a> diagrams and component descriptions.</li>
		</ul>
	</article>

	<article class="tre-card tre-step-card">
		<h3><span class="tre-card-number">3</span><i class="fa-solid fa-file-signature tre-icon-heading" aria-hidden="true"></i>Prepare Legal Agreements</h3>
		<ul>
			<li>Download and adapt template legal agreements (DSA, DTA, DUA).</li>
		</ul>
	</article>

	<article class="tre-card tre-step-card">
		<h3><span class="tre-card-number">4</span><i class="fa-solid fa-network-wired tre-icon-heading" aria-hidden="true"></i>Set Up Core Infrastructure</h3>
		<ul>
			<li>Deploy Security Server.</li>
			<li>Register with Federation Registry.</li>
			<li>Configure Trust Services and AAAI.</li>
		</ul>
	</article>

	<article class="tre-card tre-step-card">
		<h3><span class="tre-card-number">5</span><i class="fa-solid fa-plug-circle-check tre-icon-heading" aria-hidden="true"></i>Implement Interfaces</h3>
		<ul>
			<li>Integrate required APIs and data exchange protocols.</li>
		</ul>
	</article>

	<article class="tre-card tre-step-card">
		<h3><span class="tre-card-number">6</span><i class="fa-solid fa-clipboard-list tre-icon-heading" aria-hidden="true"></i>Establish Operating Procedures</h3>
		<ul>
			<li>Document operational tasks and maintenance routines.</li>
		</ul>
	</article>

	<article class="tre-card tre-step-card">
		<h3><span class="tre-card-number">7</span><i class="fa-solid fa-globe tre-icon-heading" aria-hidden="true"></i>Connect to Federation</h3>
		<ul>
			<li>Ensure compliance with federation requirements.</li>
			<li>Test inter-TRE connectivity.</li>
		</ul>
	</article>

	<article class="tre-card tre-step-card">
		<h3><span class="tre-card-number">8</span><i class="fa-solid fa-user-graduate tre-icon-heading" aria-hidden="true"></i>Train and Accredit Users</h3>
		<ul>
			<li>Verify researcher accreditation and training records.</li>
		</ul>
	</article>

	<article class="tre-card tre-step-card">
		<h3><span class="tre-card-number">9</span><i class="fa-solid fa-folder-open tre-icon-heading" aria-hidden="true"></i>Consult Appendices</h3>
		<ul>
			<li>Use <a href="appendices/reference-architecture/">Reference Architecture</a> and <a href="appendices/resources/">Resources</a> for troubleshooting and support.</li>
		</ul>
	</article>

</div>

## Modules

Use the [Relevance Matrix](relevance-matrix.md) to choose a reading path by TRE type and role.

<div class="tre-card-grid tre-card-grid-modules">

	<article class="tre-card tre-module-card tre-role-user">
		<h3><i class="fa-solid fa-book-open-reader tre-icon-heading" aria-hidden="true"></i>Module 1: TRE Fundamentals</h3>
		<p class="tre-module-meta"><span class="tre-role-label">User</span></p>
		<ul>
			<li>Understand TRE concepts and safe use.</li>
			<li>Review key terminology in the <a href="appendices/glossary/">Glossary</a>.</li>
			<li><a href="fundamentals/">Open TRE Fundamentals</a></li>
		</ul>
	</article>

	<article class="tre-card tre-module-card tre-role-builder">
		<h3><i class="fa-solid fa-diagram-project tre-icon-heading" aria-hidden="true"></i>Module 2: Architecture and Setup</h3>
		<p class="tre-module-meta"><span class="tre-role-label">TRE Builder</span></p>
		<ul>
			<li>Zones and core components: <a href="modules/architecture/">Architecture</a></li>
			<li>AAA integration</li>
		</ul>
	</article>

	<article class="tre-card tre-module-card tre-role-builder">
		<h3><i class="fa-solid fa-code-branch tre-icon-heading" aria-hidden="true"></i>Module 3: Interfaces and Configuration</h3>
		<p class="tre-module-meta"><span class="tre-role-label">TRE Builder</span></p>
		<ul>
			<li><a href="modules/interfaces/">Review interface definitions</a></li>
		</ul>
	</article>

	<article class="tre-card tre-module-card tre-role-operator">
		<h3><i class="fa-solid fa-gears tre-icon-heading" aria-hidden="true"></i>Module 4: Operations and Procedures</h3>
		<p class="tre-module-meta"><span class="tre-role-label">Operator</span></p>
		<ul>
			<li>Onboarding, monitoring, and incident response: <a href="modules/procedures/">Procedures</a></li>
		</ul>
	</article>

	<article class="tre-card tre-module-card tre-role-operator">
		<h3><i class="fa-solid fa-scale-balanced tre-icon-heading" aria-hidden="true"></i>Module 5: Legal and Compliance</h3>
		<p class="tre-module-meta"><span class="tre-role-label">Operator</span></p>
		<ul>
			<li>Agreements, compliance, and governance: <a href="modules/legal/">Legal</a></li>
		</ul>
	</article>

	<article class="tre-card tre-module-card tre-role-builder">
		<h3><i class="fa-solid fa-people-arrows tre-icon-heading" aria-hidden="true"></i>Module 6: Federation and Collaboration</h3>
		<p class="tre-module-meta"><span class="tre-role-label">TRE Builder</span></p>
		<ul>
			<li>Federation integration: <a href="federation/">Federation</a></li>
			<li>Data sharing and collaboration</li>
		</ul>
	</article>

</div>

## Appendices and Resources

- [Reference Architecture](appendices/reference-architecture.md)
- [Resources](appendices/resources.md)
