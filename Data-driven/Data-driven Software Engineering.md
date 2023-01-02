What does it mean to be data driven?

When a company employs a "data-driven" approach, it means it makes strategic decisions based on data analysis and interpretation. A data-driven approach enables companies to examine and organize their data with the goal of better serving their customers and consumers.

***Data Driven Engineering for Software Developers***
Why should i care?
The world was nice and simple when writing code that works according to a specification was enough to be a star developer.

Things have changed now. A lot of code has moved to services that are always connected. Even apps usually 'dial back home' to record telemetry about their usage and health. This data flows back to engineering teams who became accountable for making sense out of this data.

Engineering teams now share responsibility for driving business metrics such as revenue and engagement. Some people call it data-driven engineering. It's a fundamental shift in a role of software engineer.

Teams who can leverage data-driven engineering will delight customers by learning about them more than customers know about themselves. Teams who ignore data-driven engineering will continue based on assumptions and will eventually lose competitive nerve.

Software engineers need new skills to analyze telemetry data at scale and make changes in code that will drive desired changes in user behavior and software health.

Until recently, a Data Analyst and a Software Engineer were two distinct professions.

Data-driven software engineering is different from classy design and coding. Spending several days querying usage data and playing with it in Excel and R instead of coding, sounds like a waste of time. Or isn't it? Becoming data-driven is a big change, and change is hard.

Developers can resist becoming data-driven simply because they don't know how powerful it is and how to do it.

There are 3 popular ways to make dicisions in software: intuition, usability studies, and data. Human's intuition is awesome to brainstorm and innovate, but it is just terrible in deciding what features and designs should be implemented so they are used and loved by millions. We have different background and experience and can spend endless hours debating whos design is "better".

Usability studies are great. We should continue running them to learn what experiments to run next. However, these studies tend to be biased. These studies suffer from the measurement effect because people behave differently when they know that others are watching them.

First steps tend to be a challenge. Many pieces have to come together before you can benefit from data-driven decisions. Start with infrastructure that enables easy instrumentation and data access. It can take months to build a data pipeline from the ground up. Don't do this. Instead, shop around for a telemetry solution that works well for your platform. Telemetry data is boring. Insights are interesting and unique, but the data is just a set of events with properties. Borrow and reuse as much as possible. It should take hours, not months, to get the data flowing. Instrumentation and query are the only parts of the data pipeline that are unique to your application. This is the only code you should be required to write.

Next, you will need to define metrics to track and optimize. Measure time to success and a success rate. Put these metrics on a dashboard and bring them up at standups and team meetings. Later, you can automate this process with alerts. Add properties specific to your domain to debug data with funnels and segments. Leverage data to justify building or cutting features, fixing usability issues, and optimizing reliability and performance.

