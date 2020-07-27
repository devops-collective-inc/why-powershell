# Why Scripting? Why a Shell?

Before we dive into PowerShell itself, let’s tackle the importance of scripting and automation, an integral facet of PowerShell.

You’ve probably seen this [XKCD comic](http://xkcd.com/1205/) or something similar to justify scripting. While saving time is certainly a factor behind the importance of scripting and automation, it is hardly the only justification. 

Here are a few others to consider:

* **Consistency**. A scripted solution will run the exact same script every time. No risk of typos, forgetting to complete the task, or doing the task incorrectly. _Reduce human error_. 
* **Audit trail**. There are many tasks where having an audit trail would be helpful, perhaps including what task was performed, important results, errors that occurred, when the task ran, who ran it, and so forth. Scripts can provide this trail, and in PowerShell v5 and later, the shell itself features extensive logging capabilities.
* **Modular code**. You might spend more time on a particular function than time savings justify, but you can generally re-use or borrow ideas from the code later.
* **Documentation**. Is there documentation for the task? Is it up to date? A well written and commented script can generally serve as a helpful base level of documentation that might not exist for a manual task. In some cases, the script can document the process that it automates, helping to preserve institutional knowledge.
* **Education**. Administrators who can automate tasks are almost always more well-versed in the technology as a result. That makes them better planners, architects, troubleshooters, and operators, all of which convey benefit to the organization.
* **Delegation**. With a scripted solution, you can typically delegate more functions closer to the teams best equipped to handle them. With PowerShell v3 and later specifically, scripts can enable extremely granular delegation of tasks, helping the overall IT team become more efficient and responsive.

The moral of the story is that scripting and automation is important, which is just one factor behind the value of learning PowerShell.
