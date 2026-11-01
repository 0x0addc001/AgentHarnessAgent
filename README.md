# AgentHarnessAgent

**An Agent that operates the execution harness for an Agent-native system.**

AgentHarnessAgent compiles context, plans across tools and subagents, validates observations, contains side effects, and repairs execution from durable state.

用 Agent 托管 Agent 执行底座：编译上下文、跨工具与子 Agent 规划、校验观察结果、隔离副作用，并基于持久状态修复执行。

## Agent loop

| Stage | Responsibility |
|---|---|
| Data | Tasks, tool results, memory, artifacts, traces, and environment state |
| Model | Planner, executor, critic, router, and task-specific subagents |
| Training | Tool-use traces, recovery trajectories, and policy refinement |
| Inference | Context assembly, planning, and per-step model routing |
| Harness | Codex, Claude Agent SDK, OpenHands, OpenCode, E2B, MCP, and sandboxes |
| Eval | Task success, tool accuracy, recovery rate, latency, and task cost |

## System contract

- Grant minimum privilege for the current step.
- Keep plans, artifacts, and checkpoints outside volatile context.
- Preserve a complete trace of decisions, actions, and side effects.

## Engineering principles

- Delegate to the smallest capable Agent.
- Keep security and release gates deterministic.
- Recover from evidence instead of restarting blindly.

