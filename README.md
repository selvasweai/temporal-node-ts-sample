# Temporal Node.js TypeScript Sample

This is a simple Temporal sample using Node.js and TypeScript.

## Architecture

```text
Client -> Temporal Server -> Task Queue -> Worker -> Workflow -> Activities
```

## Files

```text
src/activities.ts  Real work: validation, fetch data, notification
src/workflows.ts   Workflow orchestration logic
src/worker.ts      Worker process that runs workflows and activities
src/client.ts      Starts a workflow execution
```

## Install

```bash
npm install
```

## Start Temporal local dev server

Install Temporal CLI first, then run:

```bash
temporal server start-dev
```

Temporal UI:

```text
http://localhost:8233
```

## Start Worker

Open a second terminal:

```bash
npm run start:worker
```

## Start Client

Open a third terminal:

```bash
npm run start:client
```

Expected result:

```text
Workflow result: User data for 1001
```

Test unauthorized user:

```bash
npm run start:client -- 2002
```

Expected result:

```text
Workflow result: User is not authorized
```
