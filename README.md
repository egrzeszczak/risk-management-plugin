# risk-management-plugin

> [!WARNING]
> This is a work in progress, it is NOT RECOMMENDED to use in production.

### Description

Plugin for use with LLMs to facilitate risk management in a project. The risk management process consists of providing answers to the following questions:

* Q1. What am I trying to achieve?
* Q2. What might affect my objectives?
* Q3. Which risks are the most important to me?
* Q4. What should I do most important ones?
* Q5. Did it work?
* Q6. What has changed?

To effectively manage risks there you have to provide the context of the project to the model. Based on the context the plugin will also help you establish the direction and objectives if you haven't done that yet. 

### Skills

|Skill name|Description|
|-|-|
|**Invokable skills**||
|`/help`|Explains each step of the process and guides you which skills to use next.|
|`/establish-context`|Allows to structurize detailed information about the project. Generates [context](./skills/use-shared-resources/resources/data-models/context/model.md) in `CONTEXT.json`.|
|`/set-direction`|Suggests what objectives to acquire based on context if you're unsure what to do. Select those you deem worth pursuing. Generates a [direction](./skills/use-shared-resources/resources/data-models/direction/model.md) in `DIRECTION.json`.|
|`/set-objectives`|Structurize your objectives based on context (or infer them based on direction). Generates [objectives](./skills/use-shared-resources/resources/data-models/objective/model.md) in `OBJETIVES.json`. Provides answers to **Q1**.|
|`/identify-risks`|Identify possible [risks](./skills/use-shared-resources/resources/data-models/risk/model.md) based on your defined objectives and context. Each risk is stored in dedicated risk file (e.g. `RISK-13.json`). Answers **Q2**.|
|`/assess-risk`<br>`╰ -probability`<br>`╰ -impact`|Infer the impact and the probability of a selected risk. Determine which risks matter the most. Updates this risk's `RISK-n.json` file. Answers **Q3**. <br><br> `/assess-risk-probability` infers the probability of selected risk. Updates `RISK-n.json` file. <br>`/assess-risk-impact` infers the impact of selected risk. Updates `RISK-n.json` file.|
|**Internal skills**||
|`/use-shared-resources`|This skill is invoked by other skills in this plugin to access shared resources, specifically Markdown documents containing instructions, data models, examples, etc.|

### How to use?

1. Get the latest version of the plugin from the [Tags page on GitHub](https://github.com/egrzeszczak/risk-management-plugin/tags).
2. Load the plugin into your AI environment.
3. Instruct the model to `"/help with risk management"`.

### Additional resources

If you'd like know more about risk management, I highly recommend these resources from Dr David Hillson:
* https://risk-doctor.com/risk-doctor-books/
* https://www.youtube.com/playlist?list=PLXcr0g-yn-gT5sYJzDiTY-MrLSmcVpTgz
* https://www.youtube.com/riskdoctorvideo

Other resources:
* https://www.iso.org/standard/31000