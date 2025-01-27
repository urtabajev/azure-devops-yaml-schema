## Microsoft Open Source Code of Conduct
This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Contributing to the tasks content

The [Azure Pipelines tasks reference](https://learn.microsoft.com/azure/devops/pipelines/tasks/reference/) content is built from the articles in the [task-reference](./task-reference/) folder.

Task articles are created and updated using an automated process that runs when Azure DevOps sprints are deployed.

The task articles in the tasks reference contain a combination of read-only auto-generated content based on the metadata from the [open source tasks repo](https://github.com/microsoft/azure-pipelines-tasks/tree/master/Tasks), and editable content that can be modified and updated.

An example of read-only auto-generated content for a task is the YAML syntax section for a task.

```yml
# Bash v3
# Run a Bash script on macOS, Linux, or Windows.
- task: Bash@3
  inputs:
    #targetType: 'filePath' # 'filePath' | 'inline'. Type. Default: filePath.
    filePath: # string. Required when targetType = filePath. Script Path. 
    #arguments: # string. Optional. Use when targetType = filePath. Arguments. 
    #script: # string. Required when targetType = inline. Script. 
  # Advanced
    #workingDirectory: # string. Working Directory. 
    #failOnStderr: false # boolean. Fail on Standard Error. Default: false.
    #bashEnvValue: # string. Set value for BASH_ENV environment variable.
```

This section is fully auto-generated from the task source code and can't be modified by making a pull request into this task reference articles repo.

An example of editable content is the description for a task input. The following example shows the markdown for the `targetType` input of the `Bash@3` task.

```md
<!-- :::item name="targetType"::: -->
:::moniker range="<=azure-pipelines"

**`targetType`** - **Type**<br>
`string`. Allowed values: `filePath` (File Path), `inline`. Default value: `filePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Targets script type: file path or inline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
```

All parts of the `targetType` input are auto-generated (including aliases, default values, allowed values, and dependencies on other task inputs), except for the `editable-content` section.

```md
<!-- :::editable-content name="helpMarkDown"::: -->
Targets script type: file path or inline.
<!-- :::editable-content-end::: -->
```

Contributions can be made to the text contained within the `editable-content` tags using a pull request.

The following task article sections contain `editable-content` tags.

* Task description
* Task input descriptions
* Output parameter descriptions
* Remarks
* Examples
* See also

Article sections that do not combine auto-generated content with editable content, like remarks, examples, and see also, can contain monikers within their `editable-content` tags.

Contributions cannot be made to any article text that is outside of an `editable-content` tag. Pull requests that contain edits outside of an `editable-content` tag can't be merged and will be closed. Pull requests that contain new task articles can't be merged and will be closed. New task articles are created automatically when the Azure DevOps sprint containing the new task is deployed.

To file issues with the tasks themselves, submit feedback to [the Azure Pipeline tasks open source repository](https://github.com/microsoft/azure-pipelines-tasks/tree/master/Tasks).
