<a name="readme-top"></a>

#### Release Schedule

- Add new features
- Update and optimize features
- Routine bugfix

## Changelog
`2025-03-20`
- Optimized `User Chat` component, added `Allow file` property.
- `aarpa` library to `aae` library.

`2025-03-14`
- Added directory comparison, file comparison and merge tools.
- Updated packaged way of `TabEdit` and `EditKit`.
- Optimized `WebRPA`, added `Close Browser` component.
- Added new feature: in `WebRPA`, the browser location can be controlled when the browser starts. But user needs to write a few lines of codes. User can refer to `AgentBuilder/RpaWebSearch.js` file for specific information.
- On the home page of AI2Apps, added the function of adding Agent, which can directly select files to add back-end Agent.

`2025-03-03`
- Added new feature: when `Jumper` component is selected, user can see the target component of the jump.
- In `Projects`, added new deployment templates for voice project and drawing project.
- In `Projects`, added a special template for testing project deployments.
- Added support for deploying AI2Apps on `Ubuntu` (still in beta).
- Some bugfix.

`2025-02-20`
- Fixed an issue that `Manage Account` could not be opened.
- Optimized the startup process for local AI2Apps. When AI2Apps starts, it will open `Dashboard` page automatically.
- Introduced a new `SysTabOSChat` agent.
- Optimized the `SysTabOSChat` agent dialogue, user can input `TabOS` command directly.

`2025-02-18`
- Added exception handling for `WebRPA` wait component, including handling Timeout.
- Added new feature: automatically detecting `Conda` path, user does not need to fill in manually. 

`2025-02-17`
- Created a new project changes to using the AgentBuilder agent.
- Added new feature: when creating a new Node.js or Python project, using `setup.js` to automatically sync to the back-end.
- Supports back-end project installation and configuration mechanisms
  - Uses `setup_agent.js` and deploy via script configuration: Python drawing.
  - Uses `setup_guide.md` and follow the guide to deploy: Python voice.
- Added new feature: when the IDE starts debugging, it can automatically detect whether the project needs to be synchronized with the back-end. If synchronization is required, IDE will alert user and the user can choose synchronization immediately.
- Added `SlowMo` and `StepRun` options, it allows the debugging agent to enter a slow motion or step state as soon as the agent starts.
- Some bugfix.

`2024-12-16`
- Added wechat.

`2024-11-13`
- Optimized the error message detailed display after agent startup. 

`2024-06-20`
- Supports Web Agents to learn to control web pages via `Zero-shot` learning.
- Supports users to build Web Agents + RPA that dynamically adapt to target web pages.

`2024-06-15`
- Supports fully automatic and semi-automatic development mechanisms for Agents/components. Users can interact with Agent languages to build new Agents/components without programming.
- Supports the Release of Agents/components. Users can freely share Agents/components with each other.

`2024-05-25`
- Added new feature: Supports users in building Web Agents through built-in browser control components.
- Supports users in invoking large language models on local computers via `Ollama`.
- Supports users in utilizing existing Agents as APIs or components.

<p align="right" >
  <a href="#readme-top" style="text-decoration: none; color: gray; font-weight: bold;">
    ↑ Back to Top ↑
  </a>
</p>
