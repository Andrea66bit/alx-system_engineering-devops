In this episode, I wanted to look at how to write an Incident Report, also referred to as a Postmortem. Rather than give you something of my own creation, lets look at a Google Incident Report from early 2013, which I think serves as a great example.

Before we dive in, I should mention that I am not affiliated with Google in any way, I just liked how they handled this Incident, and I think their write up should be set forth as an example for others to follow. You can find a link to the Incident Report in the episode notes below.

Working in IT, we all know that from time to time, things go off the rails, despite our planning and best intentions. When things go really wrong, you might be asked to write an Incident Report that can be shared with senior executives, fellow staff, or even customers. I recommend you go through this process whether anyone will read these or not, since it can serve as a guide, and you will be analyzing your environment when things go wrong, and building ways to prevent the same types of failures moving forward.

When I read Google’s Incident report about a their API service outage, it struck a cord with me, because it seemed to answer all of my questions, and helped give the impression they know what they were doing. We are not going to read the entire report, but lets look at the reports structure, and several things mentioned in it.

The structure is actually surprisingly simple and yet powerful. The report is made up of five parts, an issue summary, a timeline, root cause analysis, resolution and recovery, and lastly, corrective and preventative measures. Lets review each of these parts in detail.

Issue Summary

short summary (5 sentences)
list the duration along with start and end times (include timezone)
state the impact (most user requests resulted in 500 errors, at peak 100%)
close with root cause
Timeline

list the timezone
covers the outage duration
when outage began
when staff was notified
actions, events, …
when service was restored
Root Cause

give a detailed explanation of event
do not sugarcoat
Resolution and recovery

give detailed explanation of actions taken (includes times)
Corrective and Preventative Measures

itemized list of ways to prevent it from happening again
what can we do better next time?
This Incident Report also points to the fact that Google has lots of internal systems and procedural machinery happening behind the scenes. I think of these as best practices for any company. For example, they have automated service monitoring and alerting capabilities, we know this because they listed when the outage began, and when the team was alerted via pager. They also have change management, in that they were able to see who did what when, and ultimately try and roll back the changes. In my mind this is key, if you do not have this visibility into changes, then it will take time to figure out what triggered the issue in the first place, never mind trying to roll it back. They also did not sugarcoat the fact that the configuration push was not the safest and skipped testing.

So, if you ever find yourself in a situation where you have to write an Incident Report, I highly suggest checking out Google’s Incident Report listed in the episode notes below. I would also recommend thinking about how their internal systems and procedural machinery can be replicated in your environment.

Metadata
Published
2013-11-19
Duration
5 minutes
Download
MP4 or WebM
Get Notified
Weekly mailing list
Twitter Feed
RSS feed
You may also like...
© Sysadmin Casts 2013-2021
By Justin Weissig

Episodes
All Episodes
Episode Guide
What is an Incident Postmortem?
Why Do Postmortems?
Streamline the postmortem process
The blameless postmortem
When Do You Do a Postmortem?
Who Is Responsible for the Postmortem?
Best practices and more
A postmortem (or post-mortem) is a process intended to help you learn from past incidents. It typically involves an analysis or discussion soon after an event has taken place.

Postmortems typically involve blame-free analysis and discussion soon after an incident or event has taken place. An artifact is produced that includes a detailed description of exactly what went wrong in order to cause the incident, along with a list of steps to take in order to prevent a similar incident from occurring again in the future. An analysis of how your incident response process itself worked during the incident should also be included in the discussion. The value of postmortems comes from helping institutionalize a culture of continuous improvement. This way, teams are better prepared when another incident inevitably occurs with mission- or business-critical systems.

As your systems scale and become more complex, failure is inevitable, assessment and remediation is more involved and time-consuming, and it becomes increasingly painful to repeat recurring mistakes. Not having data when you need it is expensive.

Streamlining the postmortem process is key to helping your team get the most from their postmortem time investment: spending less time conducting the postmortem, while extracting more effective learnings, is a faster path to increased operational maturity. In fact, the true value of postmortems comes from helping institutionalize a positive culture around frequent and iterative improvement.

Why Do Postmortems?
During incident response, the team is 100% focused on restoring service. They should not be wasting time and mental energy thinking about how to do something optimally or performing a deep dive on what caused the incident. Doing this could further delay remediation efforts and convolute the resolution process. That’s why postmortems are essential—they provide a peacetime opportunity to reflect once the issue is no longer impacting users. The postmortem process drives focus, instills a culture of learning, and identifies opportunities for improvement that otherwise would be lost.

Without a postmortem you fail to recognize what you’re doing right, where you could improve, and most importantly, how to avoid making the same mistakes in the future. Writing an effective postmortem allows you to learn quickly from your mistakes and improve your systems and processes. A well-designed, blameless postmortem allows teams to continuously learn, serving as a way to iteratively improve your infrastructure and incident response process. Be sure to write detailed and accurate postmortems in order to get the most benefit out of them.

Organizations may refer to the postmortem process in slightly different ways:

Learning Review
After-Action Review
Incident Review
Incident Report
Post-Incident Review
Root Cause Analysis (or RCA)
Streamline the postmortem process
The specifics around conducting postmortems vary from organization to organization. Regardless of the process, the primary purpose of postmortems should be learning, whether it’s about the systems being managed, the process being followed, or how the organization executes during a crisis. Additional goals, including identification and implementation of system or process improvements, may be realized depending on the process followed.

In general, an effective postmortem report tells a story. Incident postmortem reports should include the following:

A high-level summary of what happened
Which services and customers were affected? How long and severe was the issue? Who was involved in the response? How did we ultimately fix the problem?
A root cause analysis
What were the origins of failure? Why do we think this happened?
Steps taken to diagnose, assess, and resolve
What actions were taken? Which were effective? Which were detrimental?
A timeline of significant activity
Centralize key activities from chat conversations, incident details, and more.
Learnings and next steps
What went well? What didn’t go well? How do we prevent this issue from happening again?
The blameless postmortem
A blameless post-mortem is critical for understanding failures by trying to understand how a mistake was made, instead of who made the mistake. “You ignore the ‘this person did that’ part,” explains PagerDuty Engineering Manager Arup Chakrabarti. “What matters most is the customer impact, and that’s what you focus on.” This is a crucial tool leveraged by many leading organizations such as Etsy, a pioneer for blameless postmortems, for ensuring postmortems have the right tone, empowering engineers to give truly objective accounts of what happened by eliminating the fear of punishment.

Some make the argument that the blameless postmortem might not seem possible because humans are hardwired for blame. They advocate “blame-aware” postmortems in which teams acknowledge the instinct to blame, but focus their attention onto actionable takeaways instead.

Whichever terminology resonates with your team, the key point is that postmortem discussions should be safe spaces in which teams can be completely honest and oriented around improving for the future instead of blaming others for the past.

When Do You Do a Postmortem?
Teams should conduct a postmortem after every major incident (any incident that is a Sev-2 or Sev-1). This includes any time incident response is triggered–even if it is later discovered that severity was actually lower, it was a false alarm, or it quickly recovered without intervention. A postmortem should not be neglected in these cases because it is still an opportunity to review what did and did not work well in the incident response process. If the incident should not have triggered incident response, it is worthwhile understanding why it did so monitoring can be tuned to avoid unnecessarily triggering incident response in the future. Doing this analysis and follow-up action will help prevent alert fatigue going forward.

Postmortems are done shortly after the incident is resolved, while the context is still fresh for all responders. Just as resolving a major incident becomes top priority when it occurs, completing the postmortem is prioritized over planned work. Completing the postmortem is the final step of your incident response process. Delaying the postmortem delays key learning that will prevent the incident from recurring.

Who Is Responsible for the Postmortem?
At the end of a major incident call, or very shortly after, the Incident Commander selects and directly notifies one responder to own the postmortem. Note that the postmortem owner is not solely responsible for completing the postmortem themselves. Writing a postmortem is a collaborative effort and should include everyone involved in the incident response. While engineering will lead the analysis, the postmortem process should involve management, customer support, and business communications teams. The postmortem owner coordinates with everyone who needs to be involved to ensure it is completed in a timely manner.

It is important to designate a single owner to avoid the bystander effect. If you ask all responders or a team to do the postmortem, you risk everyone assuming someone else is doing it, therefore no one does. When selecting an owner you may choose a single individual who meets any of the following criteria:

Took a leadership role investigating during the incident
Performed a task that led to stabilizing the service
Was the primary on-call responder for the most heavily affected service
Manually triggered the incident to initiate incident response
Doing the postmortem is not a punishment, and the owner is not the person that “caused” the incident. Effective postmortems are blameless. In complex systems, there is never a single cause, but a combination of factors that lead to failure. The owner is simply an accountable individual who performs select administrative tasks, follows up for information, and drives the postmortem to completion. Writing the postmortem will ultimately be a collaborative effort, but selecting a single owner to orchestrate this collaboration helps ensure it is done.

Best practices and more
PageDuty offers a completely free postmortem handbook that shares industry best practices and includes a postmortem template. Use it to help you formalize your own postmortem process to make it as easy as possible for your team to respond to issues. Even better, postmortems are now part of the PagerDuty platform — sign up for a free 14-day trial and streamline the entire postmortem process with automated timeline building, collaborative editing, actionable insights, and more.
