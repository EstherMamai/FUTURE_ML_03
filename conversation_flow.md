# 💬 Chatbot Conversation Flow

This document illustrates the complete conversation flow of the Customer Support Chatbot, showing how it handles different user scenarios.

---

## 🔄 Flow Diagram

```
User Opens Chat
      ↓
[Welcome Message Triggered]
      ↓
User Asks Question
      ↓
[Intent Recognition]
      ↓
   ┌─────────────┐
   │ Match Found? │
   └─────┬───────┘
         │
    ┌────┴─────┐
    │          │
   YES        NO
    │          │
    ↓          ↓
[Response]  [Fallback]
    │          │
    └────┬─────┘
         ↓
   Continue or End
```

---

## 📋 Conversation Scenarios

### Scenario 1: Happy Path - Order Tracking

```
User → "Hello"
Bot → "Hi! 👋 Welcome to our Customer Support Chatbot.

       I'm here to help you with:
       • Order tracking
       • Refund and return policies
       • Contacting customer support
       
       How can I assist you today?"

User → "Where is my order?"
Bot → "📦 You can track your order using the tracking link sent to your 
       email after purchase.
       
       If you still need help, please share your Order ID and we'll 
       assist you further.
       
       Is there anything else I can help you with?"

User → "Thank you"
Bot → "You're welcome! If you need anything else, feel free to ask!"
```

**Intents Used:**
- Default Welcome Intent
- Order Status Intent

---

### Scenario 2: Refund Inquiry

```
User → "Hi there"
Bot → "Hi! 👋 Welcome to our Customer Support Chatbot.

       I'm here to help you with:
       • Order tracking
       • Refund and return policies
       • Contacting customer support
       
       How can I assist you today?"

User → "I want to return an item and get a refund"
Bot → "💸 We offer refunds within 7 days of delivery.
       
       To be eligible:
       • The item must be unused
       • It should be in its original packaging
       
       Once approved, refunds are processed within 3–5 business days.
       
       If you'd like to start a return, please contact our support team 
       with your Order ID."

User → "How do I contact support?"
Bot → "📞 You can reach our customer support team using the details below:
       
       📧 Email: support@example.com
       ☎️ Phone: +254 7XX XXX XXX
       
       Our team is available Monday to Friday, 9 AM – 5 PM.
       
       We're happy to help and will get back to you as soon as possible 🙂"

User → "Perfect, thanks!"
Bot → "You're welcome! If you need anything else, feel free to ask!"
```

**Intents Used:**
- Default Welcome Intent
- Refund Policy Intent
- Contact Support Intent

---

### Scenario 3: Contact Support Escalation

```
User → "Hey"
Bot → "Hi! 👋 Welcome to our Customer Support Chatbot.

       I'm here to help you with:
       • Order tracking
       • Refund and return policies
       • Contacting customer support
       
       How can I assist you today?"

User → "I need to talk to someone"
Bot → "📞 You can reach our customer support team using the details below:
       
       📧 Email: support@example.com
       ☎️ Phone: +254 7XX XXX XXX
       
       Our team is available Monday to Friday, 9 AM – 5 PM.
       
       We're happy to help and will get back to you as soon as possible 🙂"

User → "Okay, thanks!"
Bot → "You're welcome! Feel free to reach out anytime!"
```

**Intents Used:**
- Default Welcome Intent
- Contact Support Intent

---

### Scenario 4: Fallback Handling

```
User → "Hello"
Bot → "Hi! 👋 Welcome to our Customer Support Chatbot.

       I'm here to help you with:
       • Order tracking
       • Refund and return policies
       • Contacting customer support
       
       How can I assist you today?"

User → "What's the weather like?"
Bot → "Sorry 😕 I didn't quite understand that.
       
       I can help you with:
       • Tracking your order
       • Refund and return policies
       • Contacting customer support
       
       Please try asking one of these.
       
       If you still need help, you can type 'contact support' to reach 
       our team."

User → "Sorry, I meant to ask about my order status"
Bot → "📦 You can track your order using the tracking link sent to your 
       email after purchase.
       
       If you still need help, please share your Order ID and we'll 
       assist you further."
```

**Intents Used:**
- Default Welcome Intent
- Default Fallback Intent
- Order Status Intent

---

## 🎯 Key Flow Principles

### 1. **Always Start with Welcome**
Every conversation begins with a friendly greeting to set the tone.

### 2. **Intent Recognition**
The bot analyzes user input to determine their need:
- Keywords matching
- Phrase similarity
- Context awareness

### 3. **Clear Responses**
Each response is:
- ✅ Concise and actionable
- ✅ Formatted for easy reading
- ✅ Includes next steps when relevant

### 4. **Fallback Strategy**
When the bot doesn't understand:
1. Acknowledge the confusion politely
2. Suggest rephrasing
3. Offer alternative help options
4. Provide human support contact

### 5. **Natural Endings**
Conversations conclude with:
- Confirmation that the issue is resolved
- Invitation to ask more questions
- Friendly goodbye message

---

## 🔀 Intent Transition Map

```
Welcome
  ├─→ Order Status
  ├─→ Refund Policy
  ├─→ Contact Support
  └─→ Fallback (if unclear)

Order Status
  ├─→ Contact Support (for additional help)
  └─→ Welcome (to continue)

Refund Policy
  ├─→ Contact Support (to initiate return)
  └─→ Welcome (to continue)

Contact Support
  └─→ Welcome (to continue)

Any Intent
  └─→ Fallback (if user says something unexpected)

Fallback
  ├─→ Try to understand again
  ├─→ Offer help menu (3 capabilities)
  └─→ Suggest "contact support" for human help
```

---

## 📊 Conversation Metrics

**Average Conversation Length:** 3-5 exchanges  
**Intent Recognition Accuracy:** 85-95% (with good training)  
**Fallback Rate:** 5-15% (acceptable range)  
**User Satisfaction:** Improved with clear, helpful responses

---

## 🎨 Design Philosophy

### Conversational Principles Used:

1. **Be Human-Like** - Use friendly, conversational language
2. **Be Helpful** - Always provide actionable next steps
3. **Be Clear** - Avoid jargon, use simple language
4. **Be Empathetic** - Acknowledge user frustrations
5. **Be Efficient** - Get to the point quickly

### Response Structure:

```
[Acknowledgment] → [Main Information] → [Next Steps/CTA]

Example:
"I understand you need help with tracking. → You can track your 
order in 'My Orders'. → Would you like me to guide you through 
the process?"
```

---

## 🔧 Testing Scenarios

When testing your chatbot, try these:

✅ **Basic Questions** - Test each intent individually  
✅ **Variations** - Try different ways of asking the same thing  
✅ **Typos** - See how it handles misspellings  
✅ **Context Switching** - Ask multiple unrelated questions  
✅ **Edge Cases** - Try unusual or unexpected inputs  
✅ **Follow-ups** - Test multi-turn conversations  

---

## 📝 Notes for Developers

**When Adding New Intents:**
1. Define clear purpose
2. Add diverse training phrases (10-20 minimum)
3. Write helpful, actionable responses
4. Test with real user variations
5. Monitor and improve based on actual usage

**Best Practices:**
- Keep responses under 3-4 sentences
- Use bullet points for multiple items
- Always provide an escape route (human support)
- Update regularly based on user feedback

---

*This flow represents the core conversation patterns. Real conversations may vary based on user input and context.*
