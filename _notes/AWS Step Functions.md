---
title: AWS Step Functions
tree_state: 🌱
---

If your application needs to call a bunch of different services that are dependent on one another, you could have the application handle the calls to different services conventionally. But, this would require writing a lot of code to call the different services as well as having to write code that handles error conditions (like what to do when this specific service fails) as different services are called. Step functions simplify this process dramatically, where you basically only need a config file for each service you want to call (step). Then you're ready to call the step function and run all your services.