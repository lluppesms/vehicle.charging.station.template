# Using SQUAD

See (https://github.com/bradygaster/squad/)[https://github.com/bradygaster/squad/]

## 1. Install Squad

```bash
npm install -g @bradygaster/squad-cli
squad init
```
## 2. Authenticate with GitHub (for Issues, PRs, and Ralph)

```bash
gh auth login
```

**✓ Validate:** Run `gh auth status` — you should see "Logged in to github.com".

## 3. Open Copilot with the Agent

```
copilot --agent squad --yolo
```

  > **Why `--yolo`?** Squad makes many tool calls in a typical session. Without it, Copilot will prompt you to approve each one.

**✓ Validate:** Squad responds with team member proposals. Type `yes` to confirm — they're ready to work.

Squad proposes a team — each member named from a persistent thematic cast. You say **yes**. They're ready.

## 4a. Get to work!

In the chat, use a prompt like this:

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

---

## 4b. Azure DevOps Example

In the chat, use a prompt like this:

```text
I'm starting a new project. Set up the team based on the Firefly universe.

Here's what I'm building: please review the docs/prd-vehicle-charging.md file for the product requirements.
For the initial MVP, focus implementation on the Dashboard tab only.
Make Cars, Stations, Simulation, and Settings functional placeholder tabs with clear future-stage messaging.
Try to make it look nice and graphical and as close to the live-target-state.png as you can. 
The road should have three lanes and look nice so the cars look good crossing the road. 
Please implement a queueing system so that cars will wait in line when the bays are full. 
When a bay is available move one car into that bay and make sure the others cars wait for their turn.

First, come up with an excellent implementation plan by getting two different pseudocode proposals using Opus 4.7 and GPT-5.5 on how we might implement this application. Use the same structure in each one of these proposals, then have each subagent create its own proposal in the model approaches folder. When both proposals are complete, critique each of those approaches using the Opus 4.7 model and create a third combined approach that utilizes the best of both of the proposals.  Document that unified implementation plan and store that in the docs folder.

Once the design proposal is complete, create a project board in Azure DevOps with the same structure as the implementation plan. Create work items for each of the tasks in the implementation plan and assign them to the appropriate team members. Make sure each work item has a clear description, acceptance criteria, and due date. After the work items are created, please ask me to review the project board and make any necessary adjustments before beginning implementation.  Break down the implementation into three two-week sprints and create sprint backlogs for each sprint. Organize the work items into Epics and features that are easily summarized and viewed on the project board.  

For the user interface, create five different design mockups and store those in the docs folder also. Save an image of each of those designs and then combine them into a markdown document that is easy for me to review. Before beginning implementation, please ask me which design I like best and then implement that design.

After the project board is set up and the graphical mockups are ready, please ask me to review them and make any necessary adjustments and select a design before beginning implementation.

Once I've approved the UI designs and the project board, please begin implementation. As you work through the implementation, please provide me with regular updates on your progress and any challenges you encounter. After each sprint, please provide me with a demo of the completed work and store that sprint summary info in the docs folder. Continue this process until the MVP is complete and ready for release.
```

---
