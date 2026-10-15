# ChunkWise Simulation

A no-build, client-side system simulation based on the supplied Breakscale design. The app fixes the topology to the five supplied components and four supplied connections while allowing offered load and component settings to be changed.

## Run locally

Open `index.html` in a browser. No package installation or backend is required.

## Deploy to Vercel

1. Create a GitHub repository and upload this folder's files.
2. In Vercel, import the repository.
3. Choose **Other** as the framework preset. Leave build command and output directory blank (or set output directory to `.`).
4. Deploy. `vercel.json` configures clean static hosting.

You can also deploy with the Vercel CLI from this folder using `vercel`.

## Included interactions

- Fixed five-node, four-edge topology. The UI has no add, remove, or connection-edit controls.
- Adjustable offered load and component parameters.
- Start, pause, and reset controls; latency percentiles, goodput, queue depth, and utilization.
- Export a `.breakscale`-compatible JSON design and import settings from a Breakscale JSON file without replacing the fixed topology.
- Component configuration is saved in this browser's local storage.

## Modeling assumptions

This is an educational approximation, not a reimplementation of Breakscale's discrete-event model. Arrivals are sampled each second. Processing capacity is derived from slots divided by service time. The engine sends an assumed 65% of its completed work to object storage to represent new chunks; this is not a benchmark measurement. Latency percentiles are estimated from simulated requests and should be labelled as simulated in reports.

