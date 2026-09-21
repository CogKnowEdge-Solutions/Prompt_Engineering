# Exercises: Fill-in-the-Pattern & Fix-the-Prompt

## Exercise 1: Fill-in-the-Pattern (Few-Shot Templates)

Complete the following few-shot templates with appropriate examples.

---

### 1.1: Email Priority Classifier

**Template:**
```
Classify each email by priority: High, Medium, or Low.

Examples:
Email: "[EXAMPLE_1]" → [PRIORITY_1]
Email: "[EXAMPLE_2]" → [PRIORITY_2]
Email: "[EXAMPLE_3]" → [PRIORITY_3]

Email: "[YOUR TEST EMAIL]" →
```

**Complete the template to classify emails by priority. Include at least one example for each priority level.**

**Your Completed Template:**
```
[Write your completed template with examples]
```

---

### 1.2: Topic Classifier

**Template:**
```
Classify the following customer message into a department:
Sales, Support, Billing, or Technical

Examples:
Message: "[EXAMPLE_1]" → [DEPARTMENT_1]
Message: "[EXAMPLE_2]" → [DEPARTMENT_2]
Message: "[EXAMPLE_3]" → [DEPARTMENT_3]
Message: "[EXAMPLE_4]" → [DEPARTMENT_4]

Message: "[YOUR TEST MESSAGE]" →
```

**Complete the template to route customer messages to the right department.**

**Your Completed Template:**
```
[Write your completed template with examples]
```

---

### 1.3: Tone Detector

**Template:**
```
Identify the tone of each message: Formal, Casual, Urgent, or Friendly.

Examples:
Message: "[EXAMPLE_1]" → [TONE_1]
Message: "[EXAMPLE_2]" → [TONE_2]
Message: "[EXAMPLE_3]" → [TONE_3]
Message: "[EXAMPLE_4]" → [TONE_4]

Message: "[YOUR TEST MESSAGE]" →
```

**Complete the template to detect message tone.**

**Your Completed Template:**
```
[Write your completed template with examples]
```

---

### 1.4: Code Review Classifier

**Template:**
```
Classify code review comments as: Bug, Improvement, Question, or Nitpick

Examples:
Comment: "[EXAMPLE_1]" → [CATEGORY_1]
Comment: "[EXAMPLE_2]" → [CATEGORY_2]
Comment: "[EXAMPLE_3]" → [CATEGORY_3]
Comment: "[EXAMPLE_4]" → [CATEGORY_4]

Comment: "[YOUR TEST COMMENT]" →
```

**Complete the template to classify code review comments.**

**Your Completed Template:**
```
[Write your completed template with examples]
```

---

## Exercise 2: Fix-the-Prompt

Improve the following poorly written few-shot prompts.

---

### 2.1: Fix the Inconsistent Classifier

**Original Prompt:**
```
Classify these reviews:

Review: "Great!" → Positive
Review: "Terrible" => Negative
Review: "Okay" - Neutral
Review: "Amazing product" → Positive
```

**Issues:**
- Inconsistent arrow formats (→, =>, -)
- Mixed formatting

**Your Fixed Version:**
```
[Write your fixed prompt]
```

---

### 2.2: Fix the Biased Classifier

**Original Prompt:**
```
Classify the sentiment:

Text: "I love it!" → Positive
Text: "It's amazing!" → Positive
Text: "Best thing ever!" → Positive
Text: "Wonderful!" → Positive

Text: "It's okay" →
```

**Issues:**
- All examples are positive
- No negative or neutral examples
- Model will likely classify everything as positive

**Your Fixed Version:**
```
[Write your fixed prompt]
```

---

### 2.3: Fix the Missing Delimiters

**Original Prompt:**
```
Summarize this article in 3 bullet points
The quick brown fox jumps over the lazy dog. This sentence contains every letter of the English alphabet. It has been used for decades to test fonts and typewriters. The phrase is also known as a pangram.
Summary:
```

**Issues:**
- No clear separation between instructions and content
- Model might include instructions in summary

**Your Fixed Version:**
```
[Write your fixed prompt with proper delimiters]
```

---

### 2.4: Fix the Vague Examples

**Original Prompt:**
```
Classify customer feedback:

Feedback: "Stuff" → Negative
Feedback: "Things" → Negative
Feedback: "It" → Negative

Feedback: "Great service" →
```

**Issues:**
- Examples are too vague to learn from
- No clear pattern
- All negative

**Your Fixed Version:**
```
[Write your fixed prompt with clear, specific examples]
```

---

### 2.5: Fix the Missing Edge Cases

**Original Prompt:**
```
Classify email intent:

Email: "Buy now!" → Purchase
Email: "How much?" → Inquiry
Email: "I want to buy" → Purchase

Email: "I bought this last week and it broke, I want a refund" →
```

**Issues:**
- No example for refund/return requests
- Missing mixed intents
- Model may misclassify complex cases

**Your Fixed Version:**
```
[Write your fixed prompt with edge cases]
```

---

### 2.6: Fix the Overloaded Prompt

**Original Prompt:**
```
Classify this text by sentiment, topic, urgency, language, and formality level:
"The quarterly report shows a 15% decline in revenue. We need to address this immediately."
```

**Issues:**
- Too many classifications at once
- No examples for any of them
- Model will struggle with multiple dimensions

**Your Fixed Version:**
```
[Write your fixed prompt - consider splitting into separate tasks]
```

---

## Reflection Questions

1. What's the most common mistake in few-shot prompts?

2. How do you know when you have enough examples?

3. When should you use delimiters vs XML tags?

4. What makes an example "good" vs "bad"?

---

# Challenge: Improve Classifier Accuracy

## Task

You have a customer support ticket classifier that needs to achieve 90%+ accuracy on the test set below.

### Starting Classifier (Currently 60% accuracy)

```
Classify support tickets by category: Technical, Billing, General

Examples:
Ticket: "My internet isn't working" → Technical
Ticket: "How much do I owe?" → Billing
Ticket: "What are your hours?" → General

Ticket: "{{TICKET}}"
Category:
```

### Test Set (20 tickets)

| # | Ticket | Correct Category |
|---|--------|------------------|
| 1 | "WiFi keeps disconnecting" | Technical |
| 2 | "I was charged twice" | Billing |
| 3 | "Where is your office?" | General |
| 4 | "App crashes on startup" | Technical |
| 5 | "Need refund for overcharge" | Billing |
| 6 | "How do I reset password?" | Technical |
| 7 | "My bill is wrong this month" | Billing |
| 8 | "Do you support Mac?" | General |
| 9 | "Error code 500 on login" | Technical |
| 10 | "Can I pay by check?" | Billing |
| 11 | "What's your return policy?" | General |
| 12 | "Screen goes black during call" | Technical |
| 13 | "I want to cancel my subscription" | Billing |
| 14 | "How do I contact support?" | General |
| 15 | "Bluetooth won't pair" | Technical |
| 16 | "Invoice #12345 is incorrect" | Billing |
| 17 | "Do you have a mobile app?" | General |
| 18 | "Can't update the software" | Technical |
| 19 | "Why was I charged $50 extra?" | Billing |
| 20 | "What plans do you offer?" | General |

---

## Your Task

### Step 1: Test the Current Classifier

Run each of the 20 tickets through the starting classifier. Record accuracy.

**Current accuracy: ___/20 (___%)**

### Step 2: Analyze Failures

Which tickets did it get wrong? Why?

| Wrong Ticket | Model Said | Correct | Why It Failed |
|--------------|------------|---------|---------------|
| | | | |
| | | | |
| | | | |

### Step 3: Improve the Classifier

Adjust your examples to fix the failures. Consider:
- Adding edge cases that were misclassified
- Improving example diversity
- Adding more examples for confusing categories
- Using delimiters or XML tags for clarity

**Your Improved Classifier:**
```
[Write your improved classifier prompt]
```

### Step 4: Test Again

**New accuracy: ___/20 (___%)**

### Step 5: Document Changes

| Change | Why | Impact |
|--------|-----|--------|
| | | |
| | | |
| | | |

---

## Evaluation Criteria

| Criteria | Points |
|----------|--------|
| Achieves 80%+ accuracy | 10 |
| Achieves 90%+ accuracy | 15 |
| Uses diverse examples | 5 |
| Includes edge cases | 5 |
| Clear documentation of changes | 5 |
| **Total** | **40** |

---

## Bonus Challenge

1. Can you achieve 95%+ accuracy?
2. What's the minimum number of examples needed for 90%+ accuracy?
3. Can you create a classifier that also extracts urgency (High/Medium/Low)?
