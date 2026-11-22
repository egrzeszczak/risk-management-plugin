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

### Skills

|Skill name|Description|
|-|-|
|`help`|Explains each step of the risk management and which skills to use next. Equivalent of `--help`.|
|`establish-context`|Allows to structurize detailed information about the project for later use. Generates `context` in `CONTEXT.json`.|
|`set-direction`|Suggests what objectives to acquire based on `context`. Select those worth pursuing. Generates `direction` in `DIRECTION.json`.|
|`set-objectives`|Structurize your `objectives` based on `context` (and OPTIONALLY on `direction`). Generates `objectives` in `OBJETIVES.json`.|
|`identify-risks`|TODO: Identify the effects of uncertainties on your defined objectives within the context. Generates `risks` in `RISKS.json`|
|`assess-risks`|TODO: Assess which risks matter the most. Updates `RISKS.json`|
|`plan-risk-strategies`|TODO: Plan risks strategies.|
|`use-shared-resources`|Internal utility skill, that is invoked by other skills in this plugin to access shared resources, specifically Markdown documents containing instructions, data models, examples, etc.|

### How to use?

1. Get the latest version of the plugin from the [Releases page on GitHub](https://github.com/egrzeszczak/risk-management-plugin/tags).
2. Load the plugin into your AI environment.
3. Invoke the `/how-to-manage-risk` skill in the conversation.

### Additional resources

If you'd like know more about risk management, I highly recommend these resources from Dr David Hillson:
* https://risk-doctor.com/risk-doctor-books/
* https://www.youtube.com/playlist?list=PLXcr0g-yn-gT5sYJzDiTY-MrLSmcVpTgz
* https://www.youtube.com/riskdoctorvideo

Other resources:
* https://www.iso.org/standard/31000