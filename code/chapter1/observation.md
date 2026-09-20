## Observation

The code is a simple ReAct-style agent loop, where each loop includes:

1. Thought: the LLM's reasoning
2. Action: either call a tool or finish
3. Observation: tool result fed back to the LLM

## Loop:

**Input**: User input + system prompt

**Output**:
```
Thought: I need the weather in Tokyo before recommending attractions.
Action: get_weather(city="Tokyo")
```


**Strip**: Strip the thought and action, thought -> string, action -> tool_name, kwargs

**Excute**: run action function with kwargs, take the output as Observeration

**History**: 
```
User: What attractions should I visit in Tokyo today?
Thought: I need the weather in Tokyo before recommending attractions.
Action: get_weather(city="Tokyo")
Observation: Sunny, 28°C
```