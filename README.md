# AI Model API Platforms: 7 Compared for Image and Video Jobs (2026)

AI model API platforms give you one key for many image and video models, and this list compares 7 of them by what one call can run and how the job reports back, using vendor docs checked in October 2026. Wireflow is first because one request runs a whole saved multi-model workflow, and a signed webhook returns every node's output.

1. **Wireflow**: Best overall for running several models from one API call, a hosted node board with a REST API and webhooks
2. **fal**: Best for reaching 1,000+ media models through one queue, an API with signed webhooks and automatic retries
3. **Replicate**: Best for open models and for deploying your own, a prediction API with Cog for packaging
4. **Runware**: Best for sending many image tasks in one request, pay-as-you-go APIs built on task arrays
5. **WaveSpeedAI**: Best for checking a price before a run, one API key across 1000+ models
6. **Together AI**: Best for open models and FLUX images on a prepaid balance, a one-POST image endpoint
7. **DeepInfra**: Best for pay-per-use open models with no contract, an inference cloud with webhooks on its native API

The Wireflow team maintains this list, so read entry 1 with that in mind. [Wireflow's AI workflow builder page](https://www.wireflow.ai/ai-workflow-builder) shows the board that entry 1 describes, and every other entry links to its vendor's own pages so that each cell can be checked.

The tables below are generated from [`data/tools.json`](data/tools.json). Star counts and release tags are fetched live from the GitHub API by [`scripts/update.js`](scripts/update.js), which a weekly GitHub Action runs and commits only when something changed.

<!-- LAST-CHECKED:START -->
Live repository data last checked **2026-11-09** by [`scripts/update.js`](scripts/update.js), which runs weekly via GitHub Actions.
<!-- LAST-CHECKED:END -->

Maintained by [a1adams](https://github.com/a1adams). Corrections are welcome, see [CONTRIBUTING.md](CONTRIBUTING.md).

## Contents

- [The data](#the-data)
- [Capability scores](#capability-scores)
- [Comparison table](#comparison-table)
- [The tools](#the-tools)
  - [Wireflow](#1-wireflow)
  - [fal](#2-fal)
  - [Replicate](#3-replicate)
  - [Runware](#4-runware)
  - [WaveSpeedAI](#5-wavespeedai)
  - [Together AI](#6-together-ai)
  - [DeepInfra](#7-deepinfra)
- [What each check means](#what-each-check-means)
- [How this list is maintained](#how-this-list-is-maintained)
- [FAQ](#faq)
- [Contributing](#contributing)
- [License](#license)

## The data

One row per tool, one column per thing people actually check before committing. Columns with nothing verified behind them are dropped rather than filled with guesses.

<!-- DATA-TABLE:START -->
| Tool | Claude connection | REST API | Free tier | Model support | Pricing | Open-source SDK / MCP |
|---|---|---|---|---|---|---|
| **[Wireflow](#1-wireflow)** | Custom connector, OAuth sign-in | Yes | [check](https://www.wireflow.ai/pricing) | 100+ image, video and audio models as nodes | [pricing](https://www.wireflow.ai/pricing) | n/a |
| **[fal](#2-fal)** | Hosted MCP, Streamable HTTP, OAuth | Yes | [check](https://fal.ai/pricing) | 1,000+ image, video, audio and 3D models | [pricing](https://fal.ai/pricing) | [fal-ai/fal](https://github.com/fal-ai/fal), 981 ★, fal_v1.84.0 |
| **[Replicate](#3-replicate)** | Remote MCP server or replicate-mcp npm package | Yes | [check](https://replicate.com/pricing) | Over 100 official models plus community models | [pricing](https://replicate.com/pricing) | [replicate/replicate-python](https://github.com/replicate/replicate-python), 918 ★, 1.0.7 |
| **[Runware](#4-runware)** | Hosted MCP, OAuth 2.1 | Yes | [check](https://runware.ai/pricing) | Image, video, audio, LLM and 3D models | [pricing](https://runware.ai/pricing) | [runware/runware-python](https://github.com/runware/runware-python), 3 ★, pushed 2026-11-05 |
| **[WaveSpeedAI](#5-wavespeedai)** | MCP server via npx | Yes | [check](https://wavespeed.ai/docs/how-pricing-works) | 1000+ image, video, audio, 3D and LLM models | [pricing](https://wavespeed.ai/docs/how-pricing-works) | [WaveSpeedAI/mcp-server](https://github.com/WaveSpeedAI/mcp-server), 36 ★, pushed 2026-11-09 |
| **[Together AI](#6-together-ai)** | n/a | Yes | [check](https://www.together.ai/pricing) | Open models and FLUX image models | [pricing](https://www.together.ai/pricing) | n/a |
| **[DeepInfra](#7-deepinfra)** | n/a | Yes | [check](https://deepinfra.com/pricing) | Text, image, video, speech and embedding models | [pricing](https://deepinfra.com/pricing) | n/a |
<!-- DATA-TABLE:END -->

## Capability scores

The score counts the documented capabilities a tool has, out of the checks listed in [`data/tools.json`](data/tools.json) under `capabilityChecks`. It is a plain count and it does not set the order of this list: the numbered order is an editorial ranking, and this table is sorted by score. The checks and every answer are in the file, so each cell can be checked. Disagree with a cell? Open an issue naming the tool, the check and the evidence.

<!-- CAPABILITY-SCORES:START -->
| Tool | REST API | Official SDK | Completion webhook | MCP server | Multi-model run from one call | Deploy your own model | Many tasks in one request | Score |
|------|---|---|---|---|---|---|---|-------|
| **[fal](#2-fal)** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | n/a | **6/7** |
| **[Runware](#4-runware)** | ✅ | ✅ | ✅ | ✅ | n/a | ✅ | ✅ | **6/7** |
| **[Replicate](#3-replicate)** | ✅ | ✅ | ✅ | ✅ | n/a | ✅ | n/a | **5/7** |
| **[Wireflow](#1-wireflow)** | ✅ | ❌ | ✅ | ✅ | ✅ | n/a | n/a | **4/7** |
| **[WaveSpeedAI](#5-wavespeedai)** | ✅ | n/a | ✅ | ✅ | n/a | n/a | n/a | **3/7** |
| **[DeepInfra](#7-deepinfra)** | ✅ | n/a | ✅ | n/a | n/a | n/a | n/a | **2/7** |
| **[Together AI](#6-together-ai)** | ✅ | n/a | n/a | n/a | n/a | n/a | n/a | **1/7** |
<!-- CAPABILITY-SCORES:END -->

## Comparison table

| Tool | Best for | Pricing basis | How a job reports back | What one call runs |
|---|---|---|---|---|
| **Wireflow** | Chained image and video jobs | Credits per model run | Poll, or signed webhook | A whole saved workflow |
| **fal** | Many media models behind one queue | Per image or second of video | Poll, or signed webhook | One model, or a JSON workflow |
| **Replicate** | Open models and your own models | Per output or per hardware second | Poll, or signed webhook | One prediction |
| **Runware** | Many image tasks in one request | Per request, no subscription | Poll, or webhook | An array of tasks |
| **WaveSpeedAI** | A price check before each run | Per model, from topped-up credits | Poll, or webhook | One model |
| **Together AI** | Open models and FLUX, prepaid | Per image, prepaid | Image URL in the response | One model |
| **DeepInfra** | Pay-per-use open models | Per image or execution time | Webhook on the native API | One model |

From each vendor's own pages, checked 2026-10-11, with Wireflow's pricing and model catalog read again on 2026-11-02. Prices change, so follow the pricing links in the data table.

## The tools

### 1. Wireflow

*Best overall for running several models from one API call*

![Wireflow screenshot](https://assets.wireflow.ai/competitors/wireflow-70f47ccd9660.png?v=r5)

- **What it is:** [Wireflow](https://www.wireflow.ai/) is a hosted platform where ad teams and AI agents build and rerun creative on a shared node board. Each model is a node and the output of one node feeds the next, so a saved board is a multi-model pipeline that you can start from code.
- **Best for:** Teams whose job is a chain of models, such as an image, then a video, then a voice and an edit, and who want one request to run all of it.
- **Pricing basis:** Credits per generation, set by the model you run. Starter is $36 a month with 2,660 credits, and the page says a typical mix uses about 30 credits an image and 17 credits a second of video. See the [Wireflow pricing page](https://www.wireflow.ai/pricing), checked November 2026.
- **Standout:** `POST /api/v1/workflows/{id}/run` takes only the board's input values and executes the full pipeline, returning 202 with an execution ID. The [run endpoint reference](https://www.wireflow.ai/docs/api/run) lists the request format.
- **Limit:** You run the models in the [public model catalog](https://www.wireflow.ai/models), and deploying your own model or container behind the API is not documented. There is no official SDK, so you use any HTTP client. The Free plan has no monthly credits, and full video model access starts on Starter.
- **API or automation:** A REST API with Bearer keys, an `Idempotency-Key` replay on the run endpoint and a 402 with a per-node credit breakdown when the balance is short. A webhook block POSTs each node's output URLs when the run finishes, signed with HMAC-SHA256 and retried for up to 12 attempts, as [the webhooks reference](https://www.wireflow.ai/docs/api/webhooks) explains.
- **Note:** Pricing page checked 2026-11-02: API and MCP access are on every plan, and runs spend your credits.
- **Sources:** the Wireflow pricing page and model catalog, read on 2026-11-02, and the API overview, run, executions and webhooks references, checked 2026-10-11.
- **Links:**
  - [Wireflow AI workflow builder page](https://www.wireflow.ai/ai-workflow-builder)
  - [Docs](https://www.wireflow.ai/docs/api/overview)

Pick Wireflow when the code you would otherwise write is the glue between models: wait for one job, pass its URL to the next, handle the failure. That logic moves onto the board, so a worker sends one request and receives one result. [A guide to chaining models on a board](https://www.wireflow.ai/features/ai-model-chaining) shows the pattern. If your job is one model called at high volume, entries 2 to 4 fit better, because you call the model directly.

Add the Wireflow connector to Claude Code, from the wireflowINC/skills README. Then run /mcp to sign in.
```bash
claude mcp add --transport http wireflow https://www.wireflow.ai/api/mcp
```
Or run a saved board from code: send its input values to this endpoint with an API key, then poll the execution. The request format is in the API reference linked under Docs.
```text
POST /api/v1/workflows/{id}/run
```

### 2. fal

*Best for reaching 1,000+ media models through one queue*

![fal screenshot](https://assets.wireflow.ai/competitors/fal-ai-0ec799965278.png?v=r5)

- **What it is:** [fal](https://fal.ai/) is a generative media platform for developers, with 1,000+ image, video, audio and 3D models behind one API and SDKs.
- **Best for:** Developers who want pay-per-use access to many generative models and serverless GPUs.
- **Pricing basis:** Per billing unit, such as per image or per second of video. Nano Banana 2 is $0.08 an image and Kling Video v2.5 Turbo Pro is $0.07 a second, and settings such as resolution and duration change the final cost. See the [fal pricing page](https://fal.ai/pricing), checked October 2026.
- **Standout:** Requests in the queue are never dropped and there is no queue size limit. A request that fails on a server error, a timeout or a rate limit is retried up to 10 times, and failures that return a 5xx status are not billed.
- **Limit:** New accounts start at 2 concurrent requests, and the limit rises as you buy credits, up to 40. The queue docs describe one request per generation with no single batch call, and Serverless needs approval from the fal team for each account.
- **API or automation:** Every model is an HTTP endpoint with Python and JavaScript clients. Pass a webhook URL on submit and fal POSTs a signed result, retrying failed deliveries up to 31 times, as [fal's webhook docs](https://fal.ai/docs/documentation/model-apis/inference/webhooks) explain.
- **Sources:** [fal's queue docs](https://fal.ai/docs/documentation/model-apis/inference/queue.md) and [fal's model API FAQ](https://fal.ai/docs/documentation/model-apis/faq.md), checked 2026-10-11.
- **Links:**
  - [fal-ai/fal](https://github.com/fal-ai/fal)

Pick fal over Wireflow when you call one model at a time and want a queue that retries for you. A custom fal workflow is a JSON definition that the workflows/execute endpoint runs, so you can chain models there too, which means you write and maintain that definition yourself.

Install the fal CLI, from fal's Serverless docs. Then test an app with fal run and ship it with fal deploy.
```bash
pip install fal
```

### 3. Replicate

*Best for open models and for deploying your own*

![Replicate screenshot](https://assets.wireflow.ai/competitors/replicate-da982dfb1214.png?v=r5)

- **What it is:** [Replicate](https://replicate.com/) is a platform to run and fine-tune models and to deploy custom models through a cloud API.
- **Best for:** Developers who want to call many open and official models by API, or deploy their own with Cog.
- **Pricing basis:** Per output on some models and per second of hardware on others, for example flux-dev at $0.025 an image and gpu-t4 at $0.000225 a second. See the [Replicate pricing page](https://replicate.com/pricing), checked October 2026.
- **Standout:** You package your own model with Cog, an open source tool that puts a model in a Docker container, and push it as a cloud API. Replicate also maintains over 100 official models that are always on and have a stable API.
- **Limit:** For predictions created through the API, output files are deleted after an hour, so you must save your own copies. Predictions time out after 30 minutes, a cold model answers slower while it starts, and private models bill for all time their instances are online.
- **API or automation:** Creating a prediction returns at once with an ID, and you poll or take a signed webhook. `Prefer: wait` holds the request open, 60 seconds by default. Prediction creation is limited to 600 requests a minute, as [Replicate's rate limit page](https://replicate.com/docs/topics/predictions/rate-limits) states.
- **Note:** For predictions created through the API, output files are deleted after an hour (checked 2026-10-11).
- **Sources:** [Replicate's prediction docs](https://replicate.com/docs/topics/predictions/create-a-prediction) and [its MCP reference](https://replicate.com/docs/reference/mcp), checked 2026-10-11.
- **Links:**
  - [replicate/replicate-python](https://github.com/replicate/replicate-python)

Pick Replicate over fal when you need to ship your own model and not only call hosted ones, because Cog gives you a path from container to API. A webhook can pipe one prediction's output into the next model, so the chain lives in your own code. [A comparison of Replicate and a saved board](https://www.wireflow.ai/blog/replicate-alternative) goes through that route.

Setup reference: create a prediction, from the Replicate docs. This is a documentation URL, not an executed API example.
```text
https://replicate.com/docs/topics/predictions/create-a-prediction
```

### 4. Runware

*Best for sending many image tasks in one request*

![Runware screenshot](https://assets.wireflow.ai/competitors/runware-1dad906299e3.png?v=r5)

- **What it is:** [Runware](https://runware.ai/) is an AI infrastructure platform with pay-as-you-go APIs for image, video, audio, LLM and 3D models.
- **Best for:** Developers generating images in bulk through an API.
- **Pricing basis:** Per request in USD, with no subscription and no minimum spend. FLUX 3 Image is $0.041 an image and Recraft V4.1 Flash is $0.007. See the [Runware pricing page](https://runware.ai/pricing), checked October 2026.
- **Standout:** Every Models API request is an array of tasks and each task is processed independently, so one call can batch many tasks. An error is scoped to the task that failed and the rest may still succeed.
- **Limit:** Exact cost depends on request parameters, and some models bill by compute time, so their cost is known after the run. When a model's queue is over capacity, new tasks get a 429 with a Retry-After wait. Output URLs are retained for 7 days by default.
- **API or automation:** Set `deliveryMethod` to async and poll with `getResponse`, or set `webhookURL` and Runware POSTs each completed task. A webhook can arrive more than once, so the docs say to track the task UUIDs you have processed. See [the Models API introduction](https://runware.ai/docs/models-api/introduction).
- **Note:** The linked repository is the official Python SDK. A TypeScript SDK is documented as well.
- **Sources:** [Runware's webhook docs](https://runware.ai/docs/models-api/webhooks) and [its pricing docs](https://runware.ai/docs/models-api/pricing), checked 2026-10-11.
- **Links:**
  - [runware/runware-python](https://github.com/runware/runware-python)

Pick Runware over Replicate when you already know the model and want to send a batch in one request, because the task array and per-task errors save you a fan-out loop. You still write the chain between models yourself.

Send one image task, from the Runware Models API introduction. The request body is an array, so more task objects can go in the same call.
```bash
curl https://api.runware.ai/v1 \
  -H "Authorization: Bearer $RUNWARE_API_KEY" \
  -H "Content-Type: application/json" \
  -d '[
    {
      "taskType": "imageInference",
      "taskUUID": "a770f077-f413-47de-9dac-be0b26a35da6",
      "model": "xai:grok-imagine@image-quality",
      "positivePrompt": "A golden retriever on a park bench, cinematic lighting",
      "width": 1024,
      "height": 1024
    }
  ]'
```

### 5. WaveSpeedAI

*Best for checking a price before a run*

![WaveSpeedAI screenshot](https://assets.wireflow.ai/competitors/wavespeed-2d81973fb165.png?v=r5)

- **What it is:** [WaveSpeedAI](https://wavespeed.ai/) is a platform with 1000+ image, video, audio, 3D and LLM models behind a single API key.
- **Best for:** Developers who want one API across many generative models and a price they can read first.
- **Pricing basis:** Usage-based and set per model, with no subscription: you top up credits, which never expire and are non-refundable. See [how WaveSpeedAI pricing works](https://wavespeed.ai/docs/how-pricing-works), checked October 2026.
- **Standout:** `POST /api/v3/model/price` returns the price for a model and a set of inputs, and a submission whose price cannot be calculated is rejected before a task is created or charged.
- **Limit:** Self-serve deployment of your own model is not described in the docs, and the Enterprise page offers help with it. A failed webhook delivery gets up to 3 retries, and sync mode cannot be combined with a webhook.
- **API or automation:** Add a webhook query parameter and WaveSpeedAI POSTs to your HTTPS endpoint when a task completes or fails, as [its webhook guide](https://wavespeed.ai/docs/how-to-use-webhooks) explains. Its workflow tutorial chains models as separate requests, polling each step's result.
- **Note:** The linked repository is the official MCP server. Its get_price tool quotes a price before a run.
- **Sources:** the WaveSpeedAI pricing and webhook pages linked in this entry and [its refund policy](https://wavespeed.ai/docs/refund-policy), checked 2026-10-11.
- **Links:**
  - [WaveSpeedAI/mcp-server](https://github.com/WaveSpeedAI/mcp-server)

Pick WaveSpeedAI over Runware when a worker must check the cost of each job before it runs, because the price endpoint answers that from code. Failed requests are eligible for automatic credit reversal, though a sync request that times out on the client side is not automatically refundable.

Add the WaveSpeedAI MCP server to Claude Code, from the WaveSpeedAI/mcp-server README. It runs with npx and your API key.
```bash
claude mcp add wavespeed -- npx -y @wavespeed/mcp
```

### 6. Together AI

*Best for open models and FLUX images on a prepaid balance*

![Together AI screenshot](https://assets.wireflow.ai/competitors/together-ai-b10eac5a548d.png?v=r5)

- **What it is:** [Together AI](https://www.together.ai/) provides serverless inference, dedicated inference, GPU clusters and fine-tuning for open models.
- **Best for:** Developers running open models and FLUX image models through an API.
- **Pricing basis:** Per image on the image models, and the account is fully prepaid. FLUX.2 [dev] is $0.0154 an image and FLUX.2 [pro] is $0.03, and listed image prices assume the lowest resolution and default steps. See the [Together AI pricing page](https://www.together.ai/pricing), checked October 2026.
- **Standout:** The image API is one POST to `/v1/images/generations` that names a model, and the response returns the image URL. A Batch API runs many text or audio requests from one JSONL file at up to 50% off serverless rates.
- **Limit:** Access needs a minimum $15 credit purchase and the billing docs say there are no free trials. API keys have no independent spending limits today, and API access stops when the balance reaches zero.
- **API or automation:** The images overview and batch docs describe no completion webhook and no chaining of models in one request, so a pipeline holds the state itself. See [Together's images overview](https://docs.together.ai/docs/images-overview).
- **Note:** Fully prepaid, with a minimum $15 first credit purchase; the billing docs say there are no free trials (checked 2026-10-11).
- **Sources:** [Together's billing docs](https://docs.together.ai/docs/billing-credits) and [its batch docs](https://docs.together.ai/docs/batch-inference), checked 2026-10-11.

Pick Together AI over WaveSpeedAI when you want a short request and a URL back for FLUX images, and you are happy to run the rest of the pipeline yourself. A hard stop at a zero balance is the spend control, so watch it in production.

The image endpoint, from Together's images overview: one POST that names a model, such as FLUX.2 dev, and returns the image URL.
```text
POST /v1/images/generations
```

### 7. DeepInfra

*Best for pay-per-use open models with no contract*

![DeepInfra screenshot](https://assets.wireflow.ai/competitors/deepinfra-d9bcb5ba00a2.png?v=r5)

- **What it is:** [DeepInfra](https://deepinfra.com/) is an inference cloud that hosts text, image, video, speech and embedding models behind an API.
- **Best for:** Developers who want pay-per-use access to open models, including FLUX image models.
- **Pricing basis:** Some language models by token and most other models by execution time, with no long-term contracts or upfront costs. FLUX-2-pro is $0.015 an image. See the [DeepInfra pricing page](https://deepinfra.com/pricing), checked October 2026.
- **Standout:** Every account has a default limit of 200 concurrent requests per model, and a webhook payload carries the status, the runtime and the cost of the job.
- **Limit:** You must add a card or pre-pay before using it. Webhooks work on the native API and not on the OpenAI-compatible API. The Batch API runs at 20% below real-time pricing, and image generation endpoints are not yet supported in it.
- **API or automation:** Add a webhook parameter, the API answers with status queued, and DeepInfra calls your URL when inference completes, as [its webhook docs](https://docs.deepinfra.com/account/webhooks) explain. Each inference call names one model.
- **Note:** Webhooks are a feature of the native API and are not supported with the OpenAI-compatible API (checked 2026-10-11).
- **Sources:** the DeepInfra pricing and webhook pages linked in this entry, checked 2026-10-11.

Pick DeepInfra when you want open models on a plain meter and you read the cost of each job from the webhook. It sits last only because the criterion is what one call runs, and each call here runs one model.

## What each check means

A check means the vendor's own source documents it. A cross means the source says it works another way. Anything in brackets is not published, or not verified for this list, which is not proof that it is absent.

- **REST API:** A documented HTTP API that a developer can call with a key.
- **Official SDK:** A client library the vendor publishes itself.
- **Completion webhook:** The service calls your URL when a job finishes, so a worker does not have to poll.
- **MCP server:** A documented Model Context Protocol server for agents such as Claude.
- **Multi-model run from one call:** One request runs several models in order.
- **Deploy your own model:** A documented self-serve way to host your own model or container.
- **Many tasks in one request:** One HTTP request or uploaded file can carry many independent jobs.

## How this list is maintained

Every cell comes from the vendor's own pricing page, homepage or developer docs, last checked on 11 October 2026, and Wireflow's pricing page and model catalog were read again on 2 November 2026. The numbered order is editorial and uses 4 checks: what one call runs, how a finished job reports back, what the docs say about failures and retries, and how complete the docs are. The capability score in the README is a separate plain count of documented checks, and it does not set the order. Nothing here was benchmarked, so no speed or output quality was measured.

We left out GPU rental and bare hosting products, because this list is about calling hosted models. We also left out single-vendor APIs, which [a guide to chaining models in one API call](https://www.wireflow.ai/blog/how-to-chain-multiple-ai-models-in-one-api-call) covers from the other side. To correct a cell, open an issue or a pull request with the tool, the check and a link to the vendor page that proves it. PRs are welcome, including corrections to entry 1.

- [`data/tools.json`](data/tools.json) is the source of truth. The tables in this README are generated from it and are overwritten on every run, so edit the JSON, not the tables.
- [`scripts/update.js`](scripts/update.js) fetches star counts and latest release tags from the GitHub API for the tools that publish an official repo, stamps the check date, and regenerates the tables. `--offline` regenerates without the network; `--check` exits non-zero if the README has drifted from the data.
- [`.github/workflows/refresh.yml`](.github/workflows/refresh.yml) runs it weekly and on manual dispatch, and commits only when the data actually changed.
- Prices are deliberately not stored as numbers. A stale price in a comparison table is worse than no price, so the table links to each vendor's own pricing page.

## FAQ

<details>
<summary><strong>What is an AI model API platform?</strong></summary>

It is a hosted service that gives you one account and one API key for many models, so you call a model over HTTP instead of running GPUs. fal, Replicate, Runware, WaveSpeedAI, Together AI and DeepInfra work this way, and Wireflow adds saved multi-model workflows on top.

</details>

<details>
<summary><strong>Which AI model API platforms have webhooks?</strong></summary>

Wireflow, fal, Replicate, Runware and WaveSpeedAI document a completion webhook. DeepInfra documents one on its native API and not on its OpenAI-compatible API. Together AI's images overview and batch docs do not describe one, so a worker there reads the response or polls.

</details>

<details>
<summary><strong>Can I chain several models in one API call?</strong></summary>

Wireflow runs a whole saved board from one request, and fal runs a custom workflow from a JSON definition. On the others each call names one model, so you pass one job's output to the next in your own code. A webhook can trigger that next step.

</details>

<details>
<summary><strong>Do I pay for failed generations?</strong></summary>

It depends on the platform. Wireflow charges credits when a model finishes successfully, Runware charges only for successful requests, and Replicate does not charge a failed run on public models. fal does not bill 5xx failures, and WaveSpeedAI reverses credits automatically on eligible failures.

</details>

<details>
<summary><strong>Which platform lets me deploy my own model?</strong></summary>

Replicate deploys a model you package with Cog, fal Serverless runs your own Python app or container after approval, and Runware Serverless runs your own code. Deploying your own model on Wireflow is not documented, because its API runs saved workflows built from its listed nodes.

</details>

<details>
<summary><strong>Do these platforms work with Claude through MCP?</strong></summary>

Wireflow, fal, Replicate, Runware and WaveSpeedAI each document an MCP server. Together AI and DeepInfra do not state one on the pages checked. On Wireflow, you add the connector URL and sign in with OAuth, so there is no API key to paste.

</details>

## The short version

Pick Wireflow when one request should run several models and return every output, and pick fal when you want many models behind a retrying queue. Pick Replicate when you need to deploy your own model, and Runware when one call should carry a whole batch of image tasks. Before you commit, run the same 20 jobs on your two finalists and note how each one reports a failure. To see what a saved board looks like from the API side, read [the Wireflow API overview](https://www.wireflow.ai/docs/api/overview).

## Contributing

Corrections and additions are welcome, including corrections to the entry for the tool that maintains this list. Open an issue with the tool name, a working link, one line on what it does that the tools already listed do not, and one line on where it stops. Entries are judged on whether they are usable today, not on popularity. Full rules in [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[CC0 1.0 Universal](LICENSE), public domain. Take the data, fork the list, no attribution required.

---

Maintained by [a1adams](https://github.com/a1adams).
