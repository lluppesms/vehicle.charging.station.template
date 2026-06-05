# Vehicle Charging Station Simulator Lab
<!-- ---
title: Vehicle Charging Station Simulator
description: Interactive web simulator where moving cars can be clicked to enter charging bays, recharge over time, and return to traffic while tracking total energy dispensed
author: Workshop facilitator
ms.date: 2026-06-05
ms.topic: overview
keywords:
    - ev charging
    - simulation
    - web app
    - animation
estimated_reading_time: 4
--- 
-->

## Overview

This repository contains an EV charging station simulation assignment template.

The target application is a visually rich, modern web page where:

* Cars continuously move on a roadway at the bottom of the screen.
* Cars are generated at regular intervals and move slowly across the roadway.
* A user can click a moving car to send it to an available charging slot.
* The selected car charges over about one minute while battery progress is shown live.
* The car exits the station and returns to roadway traffic when charging completes.
* A cumulative metric displays total energy dispensed across all completed sessions.

## MVP Scope

The initial MVP should focus only on the Dashboard tab.

* Dashboard tab: full charging station simulation experience
* Cars tab: functional placeholder text only
* Stations tab: functional placeholder text only
* Simulation tab: functional placeholder text only
* Settings tab: functional placeholder text only

Placeholder tabs should render clear messaging that the content will be implemented in future stages.

## Product Specifications

Primary product requirements are documented in [docs/prd-vehicle-charging.md](docs/prd-vehicle-charging.md).

Use this visual reference as the target interaction style and atmosphere:

![EV charging simulator target style](docs/images/live-target-state.png)

## Initial Implementation Scope

Initial build focus should include:

* Roadway animation engine for continuously moving traffic
* Regular car generation and controlled slow roadway movement
* Click-to-charge interaction and slot assignment behavior
* Charging lifecycle state machine (enter, charge, exit, rejoin)
* Live battery progress visualization for each active charging session
* Cumulative total energy dispensed counter
* Responsive modern UI for desktop and mobile

## Getting Started

See [https://github.com/bradygaster/squad/](https://github.com/bradygaster/squad/) for an explanation of what Squad is and how to use it.

### 1. Install Squad

Open a terminal window and use the CLI to initialize your Squad for this repository.

```bash
npm install -g @bradygaster/squad-cli
squad init
```

### 2. Authenticate with GitHub (if using GitHub!)

Authenticate before using GitHub-backed workflows such as issues, pull requests, and Ralph.

```bash
gh auth login
```

Validate the sign-in state:

```bash
gh auth status
```

You should see that you are logged in to `github.com`.

### 3. Start Copilot with Squad

Choose one of the following ways to work with the Squad agent.

#### Option A: CLI agent

```bash
copilot --agent squad --yolo
```

Use `--yolo` so Squad can make the typical series of tool calls without prompting for approval each time.

#### Option B: Copilot Chat

Open Copilot Chat in VS Code, select the `SQUAD` agent, change approvals to `Bypass approvals`, and start chatting there.

Use bypass approvals for the same reason as the CLI flow: Squad typically needs to make many tool calls during a session.

### 4. Confirm the team setup

When Squad proposes the team members, reply with `yes` to confirm the lineup and begin work.

### 5. Use a starter prompt

For a direct implementation-oriented kickoff, use a prompt like this:

```text
I'm starting a new project. Set up the team based on the Firefly universe.
Here's what I'm building: please review the docs/prd-vehicle-charging.md file for the product requirements.
For the initial MVP, focus implementation on the Dashboard tab only.
Make Cars, Stations, Simulation, and Settings functional placeholder tabs with clear future-stage messaging.
Try to make it look nice and graphical and as close to the live-target-state.png as you can.
The road should have three lanes and look nice so the cars look good crossing the road.
Please implement a queueing system so that cars will wait in line when the bays are full.
When a bay is available move one car into that bay and make sure the others cars wait for their turn.
```

### 6. Azure DevOps planning example

If you want Squad to produce a more structured planning and delivery workflow, use a prompt like this:

```text
I'm starting a new project. Set up the team based on the Firefly universe.

Here's what I'm building: please review the docs/prd-vehicle-charging.md file for the product requirements.
For the initial MVP, focus implementation on the Dashboard tab only.
Make Cars, Stations, Simulation, and Settings functional placeholder tabs with clear future-stage messaging.
Try to make it look nice and graphical and as close to the live-target-state.png as you can.
The road should have three lanes and look nice so the cars look good crossing the road.
Please implement a queueing system so that cars will wait in line when the bays are full.
When a bay is available move one car into that bay and make sure the others cars wait for their turn.

First, come up with an excellent implementation plan by getting two different pseudocode proposals using Opus 4.7 and GPT-5.5 on how we might implement this application. Use the same structure in each one of these proposals, then have each subagent create its own proposal in the model approaches folder. When both proposals are complete, critique each of those approaches using the Opus 4.7 model and create a third combined approach that utilizes the best of both of the proposals. Document that unified implementation plan and store that in the docs folder.

Once the design proposal is complete, create a project board in Azure DevOps with the same structure as the implementation plan. Create work items for each of the tasks in the implementation plan and assign them to the appropriate team members. Make sure each work item has a clear description, acceptance criteria, and due date. After the work items are created, please ask me to review the project board and make any necessary adjustments before beginning implementation. Break down the implementation into three two-week sprints and create sprint backlogs for each sprint. Organize the work items into epics and features that are easily summarized and viewed on the project board.

For the user interface, create five different design mockups and store those in the docs folder also. Save an image of each of those designs and then combine them into a markdown document that is easy for me to review. Before beginning implementation, please ask me which design I like best and then implement that design.

After the project board is set up and the graphical mockups are ready, please ask me to review them and make any necessary adjustments and select a design before beginning implementation.

Once I've approved the UI designs and the project board, please begin implementation. As you work through the implementation, please provide me with regular updates on your progress and any challenges you encounter. After each sprint, please provide me with a demo of the completed work and store that sprint summary info in the docs folder. Continue this process until the MVP is complete and ready for release.
```

## Running the Application

Once the project has been scaffolded, use the following steps to build and run it locally.

### Prerequisites

* [.NET 10 SDK](https://dotnet.microsoft.com/download) or later
* [Aspire CLI](https://learn.microsoft.com/dotnet/aspire/fundamentals/setup-tooling) (`dotnet workload install aspire`)

### Steps

1. Restore dependencies:

   ```bash
   dotnet restore
   ```

2. Build the solution:

   ```bash
   dotnet build
   ```

3. Run the tests:

   ```bash
   dotnet test ChargingTests/ --verbosity normal
   ```

4. Start the application via Aspire:

   ```bash
   aspire run
   ```

5. Open the Aspire dashboard URL printed in the console (typically `http://localhost:18888`) and then open the application URL to view the simulator.

## Contributing

* Keep PRDs in docs/ using the pattern prd-*.md.
* Keep visual references under docs/images/.
* Follow repository Copilot and coding instructions when adding source code and infrastructure artifacts.
