# Usage guide

CodeAK runs on this computer. The catalog, chat, jobs, and device budgets stay here. There is no account to sign in to. Open the desktop app, or open http://127.0.0.1:3000 in a browser on this same PC.

Use the sidebar in the order you are working. Start at Dashboard to see what is connected, then Agents or Local agent for the work, then Chat when a local model is ready.

## Dashboard

The Dashboard is the status of this PC: catalog size, installs, local agents, jobs, and recent activity.

**How it works.** The counts come from the catalog on disk and from MongoDB. When MongoDB is down, the catalog pages still open and installs stay disabled.

**Best use.** Look here first when something seems missing. A dark lamp next to Mongo, Catalog, or Bash means that part is not ready. Download for Windows is the installer for another PC, not a second copy of the server already running here.

## Agents

Agents is the catalog. Each division is a set of specialist markdown files. Open a division, read an agent, and install it into a tool on this PC.

**How it works.** The source files stay the catalog. An install copies the agent into the tool you pick, such as Cursor. Publishing a new agent from the wizard writes markdown under the catalog, either as a published file or as a draft.

**Best use.** Install one division you will actually call, then try that agent in the tool before installing more. Read the agent page before you install it so the description matches the job.

## Local agent

Local agent is where named models live. A named model is an Ollama model plus the catalog text you attach to it.

**How it works.** Ollama has to be answering on this PC. You choose a base model you already have, then attach one agent or a division. Knowledge indexes markdown into pieces the model can look up. Instruction examples and weight training are separate jobs. The first successful named model is v1. The next successful run of that same kind is the next version.

**Best use.** Download the base model and build one named model before you index a large division. For knowledge, index the text you want the model to quote. Leave out images, video, and dependency folders. Weight training is a separate, longer job. Do not start it until the named model and its knowledge already answer the way you expect.

## Chat

Chat is one thread bound to one local agent for the life of that thread.

**How it works.** You pick a local agent when you open the thread. Later messages stay with that agent. A file you send is knowledge for that chat only. It is not added to the agent's Knowledge library, and a second thread with the same agent does not see it. Text and office files can be read into the thread. Audio and video are stored and are not transcribed. An image is sent to the model only when that model reports vision.

**Best use.** Open a new thread when the subject changes. Drop the brief, the spreadsheet, or the PDF into the thread you want the agent to use, then ask about those files in that same thread. Keep the agent's permanent knowledge on the Local agent page.

## Tools

Tools is the list of places an agent can be installed, such as Cursor.

**How it works.** An install runs the catalog installer for the tool you choose. Git Bash is required for that install. The page shows whether Bash was found.

**Best use.** Install into the tool you have open. If Bash is off, install Git for Windows and reopen CodeAK before you retry. A failed install is recorded in Activity.

## Projects

Projects are the folders where you have installed agents.

**How it works.** Each project remembers which agents were installed there and for which tool. Removing a recorded install takes that copy out of the project. It does not delete the catalog file.

**Best use.** Use a project when you want a team of agents in one codebase. Check this page before you install the same division again, so you can see what is already there.

## Runbooks

Runbooks are short plans for a kind of work, such as a product build or an incident. Each runbook names the agents that fit that plan.

**How it works.** The runbook text is a playbook. It does not start a job by itself. You still install or call the agents it lists.

**Best use.** Read the runbook, then install only the agents for the step you are in. The full list is a roster, not a requirement to install every name on day one.

## Activity

Activity is the log of what CodeAK did: installs, model downloads, knowledge jobs, and connection checks.

**How it works.** Each row is a success or a failure with the time and a short line. The bell in the header shows the latest rows.

**Best use.** Open Activity when a job ends and the result is unclear. The line on the job and the row here are the same event. A failure row is the place to read the reason before you run the job again.

## Collections

Collections are saved sets of agents.

**How it works.** You group catalog agents under a name you choose. The set is a list. It does not install those agents until you install them from the catalog.

**Best use.** Save a collection for a kind of work you repeat, such as a design review. Install from the collection into a project when that work starts.

## Local Device Specifications

This page is the hardware of the computer running CodeAK, and the limits for local jobs.

**How it works.** CPU, memory, GPU, disk, and temperatures are read from this PC. A missing sensor stays Unavailable. The browser card is a separate, smaller report and can be masked by the browser. The budgets you save apply to the next local job that is admitted. They do not change a job that is already running. Chat keeps working when GPU use for jobs is turned off. Ollama itself is not inside the job limit.

**Best use.** Save budgets only after you mean them. Light, Balanced, and Performance fill the form. They are not saved until you choose Save budgets. If jobs wait on free memory, lower Minimum free RAM or close other programs. Do not treat a GPU percentage on the host chart as the memory of this app. The application bars are the CodeAK process and the Ollama process.

## Settings

Settings is the connection record for MongoDB, the catalog, Git Bash, and Ollama.

**How it works.** Each card shows whether that piece answered and when it last succeeded. The theme control is here and in the header. The catalog files are read from disk. This page does not rewrite them.

**Best use.** Open Settings when a lamp is off. MongoDB down means installs, chat history, and jobs wait. Ollama down means local models and chat wait. The catalog can still be browsed.

## Download

Download for Windows is the installer for a PC that does not already have CodeAK.

**How it works.** The button appears when a public HTTPS address is set. The file is `CodeAK-Setup.exe`. Setup checks Windows, then reuses a compatible MongoDB and Ollama when they already answer. It installs a private database or Ollama only when they are missing. A model is not inside the installer.

**Best use.** Send the installer to a Windows 10 22H2 or Windows 11 64-bit PC. Run the setup file. Open CodeAK from the shortcut. The person does not clone a repository and does not install Node. The setup file is unsigned, so Windows shows a warning before it runs.
