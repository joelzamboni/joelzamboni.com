---
title: 'The case for fewer environments'
date: 2021-03-22T00:00:00-04:00
draft: false
tags:
    - coding
    - devops
    - product
---

At Webera, we strive to build the underlying technology which supports innovation. Our team provides DevOps as a Service, a small group of two DevOps/SRE Engineers, a DevOps Architect, and a Scrum Master.

A DevOps team’s objective is to help the developers get their code to the end-users as fast, safely, and stable as possible. We use automation, infrastructure as code, testing tools, vulnerability assessment, lots of monitoring software, pipelines, ticketing systems, office hours, and many other tools to perform this task.

The place where the developer’s code and our work meets depends on each company’s workflow. We try to influence the process in many ways but always keep a keen eye on DevOps’ best practices and the value added by each step and lead time.

So in a way, the DevOps body of knowledge already provides significant pressure to push back extra work, which might have a questionable added value when we analyze the requirements for a reduced number of environments to test an application before it goes to production.

In this article, I want to focus on an argument that I picked up from the book The Scrum Fieldbook that shows, in chapter 3, how much a project can be impacted by what to some might be a minor problem: indecision.

Mr. Sutherland uses the CHAOS Report to provide insight into what causes many projects to fail. When the data of tens of thousands of projects are analyzed, there seems to be a profound correlation between project failure and extended decision-making intervals. It is astonishing since I think most issues would live in the old triangle of cost, time, and quality.

Let’s go back to the environments now. Most projects usually have three environments: development, staging, and production. But in reality, it varies. Probably at the very beginning of the project, you might have just one, and as the project matures and more external integrations or testers requirements are added, it might grow to several. Here is the problem, and I shouldn’t criticize this because our business supports these environments. Still, based on the evidence that delay in a decision is the main culprit for project failures, each new environment added to production flow further delays delivering the project. Some might argue that they need more testing or that integration with the new application. Well, you know the arguments, I don’t need to make them.

Based on the evidence, each new environment will always cause an additional delay in the decision-making process, which might cause the project to fail and, ultimately, our customers and our business to struggle.

I recommend automating as many parts of the testing process as possible and reducing the deployments’ batch size to avoid feature competition for testing resources, which will inevitably push the creation of new environments and force the developers and operations teams to support additional unnecessary work.

Let me know what you think!

