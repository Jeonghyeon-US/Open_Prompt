# Claude Prompting Guide | Claude 프롬프트 가이드

## Model Overview | 모델 개요

Claude is a family of large language models developed by Anthropic, designed with a focus on helpfulness, harmlessness, and honesty. The Claude model family includes different versions like Claude 3 Opus, Claude 3 Sonnet, Claude 3 Haiku, and others, each with varying capabilities and performance characteristics.

Claude는 Anthropic에서 개발한 대규모 언어 모델 제품군으로, 유용성, 무해성 및 정직성에 중점을 두고 설계되었습니다. Claude 모델 제품군에는 Claude 3 Opus, Claude 3 Sonnet, Claude 3 Haiku 등 다양한 버전이 포함되어 있으며, 각각 다양한 기능과 성능 특성을 가지고 있습니다.

## Strengths & Limitations | 강점 & 한계

### Strengths | 강점
- Excellent at following complex, multi-step instructions
- Strong reasoning capabilities and nuanced understanding of context
- Designed to be helpful while avoiding harmful outputs
- Good at maintaining conversation context over long exchanges
- Capable of handling various creative writing tasks with nuance
- Skilled at understanding and generating code

### Limitations | 한계
- Knowledge cutoff limitations (varies by model version)
- May sometimes be overly cautious in responses
- Sometimes struggles with precise mathematical calculations
- Cannot browse the web independently (except when using web tools feature)
- Cannot run code or access external tools (except in specialized environments)

## Unique Features | 고유 기능

- **Constitutional AI**: Claude is built using Constitutional AI, which helps it avoid harmful, unethical, or deceptive outputs.
- **XML Tagging**: Claude has strong capabilities with structured outputs using XML tags.
- **Tool Use**: Some Claude interfaces support tools like web search, code interpretation, and more.
- **Long Context Windows**: Claude models support very long context windows (up to 200K tokens in some versions).

## Optimal Prompting Techniques | 최적의 프롬프트 기법

### 1. Be Clear and Specific
Claude responds best to clear, specific instructions. Front-load your most important requirements.

```
Please create a detailed marketing plan for a new eco-friendly water bottle. 
Include the following sections:
1. Target audience analysis
2. Competitive landscape
3. Key messaging and positioning
4. Marketing channels
5. Budget allocation recommendations

The plan should focus on sustainability as the primary selling point.
```

### 2. Use XML for Structure
Claude excels with XML-based prompting for structured outputs:

```
Please analyze this financial data and provide insights in the following XML format:

<analysis>
  <summary>
    A brief 2-3 sentence overview of the key findings
  </summary>
  <key_metrics>
    <metric name="revenue_growth">Your analysis</metric>
    <metric name="profit_margin">Your analysis</metric>
    <metric name="cash_flow">Your analysis</metric>
  </key_metrics>
  <recommendations>
    <recommendation priority="high">First recommendation</recommendation>
    <recommendation priority="medium">Second recommendation</recommendation>
    <recommendation priority="low">Third recommendation</recommendation>
  </recommendations>
</analysis>
```

### 3. Persona and Role-Based Prompting
Claude responds well to being given a specific role or persona:

```
You are an experienced patent attorney specializing in software patents. 
I need your help evaluating whether my new algorithm for image processing might be patentable.

Here's the description of my algorithm:
[description]

Please analyze this from a patent law perspective, considering:
1. Novelty
2. Non-obviousness
3. Utility
4. Subject matter eligibility concerns
```

### 4. Few-Shot Examples
Provide examples of the type of output you want:

```
Please help me write professional email responses to customer inquiries. 
Here's the format I'd like you to follow:

Example 1:
Customer: "I still haven't received my order and it's been 2 weeks. Order #45678."
Response: "Dear valued customer, I sincerely apologize for the delay with your order #45678. I've checked our system and see that your package is [status]. I've taken the following steps to resolve this issue: [actions taken]. Please let me know if you need any further assistance. Regards, [Name]"

Now, please help me respond to this customer message:
"I received my order but one item is missing. Order #91011."
```

### 5. Chain-of-Thought Prompting
Ask Claude to walk through its reasoning step by step:

```
I need help solving this probability problem. Please think through this step-by-step:

If I draw 3 cards from a standard deck of 52 cards without replacement, what is the probability that I'll get exactly 2 hearts?

Walk through your reasoning in detail before providing the final answer.
```

## Examples | 예시

### Example 1: Code Generation and Explanation

```
I'm a Python beginner trying to learn about data analysis. Could you:

1. Write a simple Python script that reads a CSV file containing sales data (columns: date, product_id, amount)
2. Calculate the total sales per product
3. Create a bar chart visualization of the results
4. Save the chart as a PNG file

Please include comments explaining what each part of the code does, so I can learn from it. Also, briefly explain any libraries you're using and why they're appropriate for this task.
```

### Example 2: Role-Playing for Creative Writing

```
You are a renowned mystery novelist in the style of Agatha Christie. You specialize in clever, tightly-plotted whodunits with surprising yet logical solutions.

Help me develop a murder mystery set on a luxury space tourism vessel in the year 2075. I need:

1. A brief setting description (the spacecraft and its unique features)
2. 5 potential suspects with motives, occupations, and key personality traits
3. An unusual murder method that takes advantage of the space environment
4. A clever clue that the detective might initially overlook
5. A surprising twist for the resolution

Make the mystery fair-play, where a clever reader could theoretically solve it given the clues.
```

## Additional Resources | 추가 자료

- [Anthropic's Claude Documentation](https://docs.anthropic.com/)
- [Claude Prompt Design Guide](https://docs.anthropic.com/claude/docs/introduction-to-prompting)
- [Anthropic's System Prompts Guide](https://docs.anthropic.com/claude/docs/system-prompts)
- [Claude API Documentation](https://docs.anthropic.com/claude/reference/getting-started-with-the-api)
