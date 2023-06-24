# (ISC)2 CISSP Certified Information Systems Security Professional Official Study Guide 9th Edition by Mike Chapple, James Michael Stewart, Darril Gibson

## Chapter 2

### Q&A
_____ are the weakest link in the security chain. You should treat them _____ ____ _____.

A: Humans are the weakest link in the security chain. You should treat them not as a problem to solve, but as an ally to
defend the company.

How can you figure out what kind of access a person needs to do their job?

A: A job description is created before hiring someone. That job description describes the job responsibilities and should
include security-related responsibilities, such as handling classified material, and so it can be used to guide the
assignment of access rights.

How can an organization prevent employee privelege creep, and why should they?

A: Managers should periodically audit privelege assignments to make sure workers only have as much privelege as needed to do their job. Applying the principle of least privelege in this way is a risk reduction strategy.

What could go wrong due to an employee having more permissions than they need?

Greater chance for mistakes to damage asset confidentiality, integrity, and availability (CIA) outside of the worker's actual responsibilities, greater ability for a disgruntled worker to cause harm on purpose, and greater ability for an attack that takes over a worker's account to cause harm.

Why is it important to have a standardized interview process?

A: To treat candidates fairly and have a legally defensible reason for why someone was or wasn't hired.

Is it okay for a company to view candidate's social media accounts?

A: It's a common practice, but companies should be aware of local laws regarding discrimination during hiring.

What is a honeypot?

A: A honeypot is a network-attached system set up as a decoy to lure cyber attackers and detect, deflect and study hacking attempts to gain unauthorized access to information systems. The function of a honeypot is to represent itself on the internet as a potential target for attackers -- usually, a server or other high-value asset -- and to gather information and notify defenders of any attempts to access the honeypot by unauthorized users.

What steps do you take when hiring someone?

A: Hiring new staff typically involves several distinct steps: creating a job description or position description, setting a classification for the job, screening employment candidates, and hiring and training someone best suited for the job.

What are typical documents for employees to sign when onboarding?

A: An employeement agreement, an acceptable use policy, and a NDA are typical documents to sign when onboarding.

What is the employment agreement an employee signs during onboarding?

A: The employeement agreement outlines the rules and restrictions of the organization, the security policy, details of the job description, violations and consequences, and the minimum or probationary length of time the position is to be filled by the employee. These items might be separate documents, such as an acceptable use policy (AUP). In such a case, the employment agreement is used to verify that the employment candidate has read and understood the associated documentation and signed their agreement to adhere to the necessary policies related to their prospective job position.

What is an Acceptable Use Policy?

A: An acceptable use policy (AUP) defines what is and what is not an acceptable activity, practice, or use for company equipment and resources.

When does an employee sign a Non-Discolsure Agreement (NDA)?

A: It's common for an employee to sign a NDA as part of their onboarding. In addition, throughout a worker's employment, they may be asked to sign additional NDAs as their job responsibilities change and they are needing to access new sensitive, proprietary, or confidential assets. When an employee leaves the organization, they should be reminded of their legal obligation to maintain silence on all items covered by any signed NDAs. In fact, they may be required to re-sign the NDA upon departure as a means to legally confirm that they are fully aware of their legally recognized obligation to maintain trade secrets and other confidential information.

What is a mandatory vacation?

A: A common practice in the financial industry, mandatory vacations are used as a peer review process. This process requires a worker to be away from the office and without remote access for one to two weeks per year. While the worker is on the “vacation,” a different worker performs their work duties with their actual user account, which makes it easier to verify the work tasks and privileges of employees while attempting to detect abuse, fraud, or negligence on the part of the original employee. This technique often works better than others since it may be possible to hide violations from other accounts, but it is very difficult to commit violations and hide them from the account used to perform them.

What is collusion?

A: When several people work together to perpetrate a crime, it's called collusion.

What sectors is employee re-evaluation common in? What does it consist of?

A: For many job positions that are considered sensitive or critical, especially in medical, financial, government, and military organizations, periodic revaluation of employees may be needed. This could be a process that is just as thorough as the original background check and investigation performed when the individual was hired, or it may require performing only a few specific checks to confirm consistency in the person's qualifications as well as researching for any new information regarding disqualifications.

What is User Behavior Analytics? What else is it called?

A: User behavior analytics (UBA) is the process of tracking, collecting, and assessing user data and activities using monitoring systems. UBA is also known as user and entity behavior analytics (UEBA). UBA is a type of cybersecurity solution that discovers threats by identifying activity that deviates from a normal baseline. UBA solutions use artificial intelligence (AI) and machine learning (ML) to analyze large datasets with the goal of identifying patterns that indicate security breaches, data exfiltration, or other malicious activity.

What is offboarding? What is one of the most common elements of this process from a security perspective?

A: Offboarding is the opposite of onboarding, and occurs when an employee leaves the company. The most common element of this process from a security perspective is the removal of that person's identity from the IAM system.

When else might an employee's identity be removed from the IAM system?

A: In some cases, when an employee transfers to a new role within the company, it may be treated as a fire / rehire, and part of this process will include removing the employee's identity from the IAM system in the same way you would if they were to be fired.

What factors might a company weigh in deciding whether to treat an employee moving to a new role as a fire / rehire or a personnel move?

A: Whether the same user account will be retained, if their clearance will be adjusted, if their new work responsibilities are similar to the previous position, and if a “clean slate” account is required for auditing purposes in the new job position.

Sometimes an employee's IAM account is only disabled when they leave a company. Why is that?

A: It is common to disable accounts of prior employees in order to retain the identity for auditing purposes for a few months. After the allotted time, if no incidents are discovered in regard to the ex-employee's account, then it can be deleted from the IAM completely. If the account is deleted prematurely, any logged events that are of a security concern no longer point to an actual account and thus can make tracking down further evidence of violations more complicated.

Why should the offboarding process be well-documented?

A: The procedures for onboarding and offboarding should be clearly documented in order to ensure consistency of application as well as compliance with regulations or contractual obligations.

What communication needs to occur to prevent employees from re-entering the building after they no longer work for the company?

A: Telling security guards and other physical facility and property access management personnel to disallow re-entry.

What does the final meeting where an employee is let go look like? Who should be there?

A: In addition to the HR employee and the soon to be ex-employee, there should be at least one witness, preferably a higher-level manager and/or a security guard, at the meeting. Once the employee has been informed of their release, they should be reminded of the liabilities and restrictions placed on the former employee based on the employment agreement, NDAs, and any other security-related documentation. During this meeting, all organization-specific identification, access, or security badges as well as devices, cards, keys, and access tokens should be collected.

What should the offboarding process be like for non-voluntary terminations where there is a perceived risk of confrontation?

A: The termination process may need to be abrupt and attended by security guards. Any need to resolve HR issues, retrieve company equipment, review NDAs, and so forth can be handled afterward through an attorney.

What is an exit interview?

A: When an employee who is leaving is asked their reasons for leaving, their perspective on the company, and anything that could be done to improve the company.

Under which circumstances should an ex-employee be escorted off the property and not allowed to return to the building?

A: This is necessary in all cases, and whether the termination ended on good terms or bad.

What kind of fuck-up is common when firing an employee?

A: Companies have often initiated the offboarding process before letting the employee know. This can cause disgruntled employees, who still have not been let go, to take it out on the company. For instance companies may let layoff information leak to the media, or disable someone's badge or phone, before telling the employee that they're being let go.



