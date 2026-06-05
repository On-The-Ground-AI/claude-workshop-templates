# Cowork prompts (CW-1)

> ⚠️ AI-generated · Reviewed by Haojun Yong (OTG).

10 prompts for Claude.ai working as your coworker — Gmail, Calendar, Drive connectors enabled.

---

## 1. Long-research deep dive

**Use it when:** You need to understand a topic, market, or company in depth — used to take you half a day.

**The prompt:**
```
Do a thorough research pass on [TOPIC]. Cover:
1. The 5–7 most important sub-topics, with one paragraph each.
2. The 3 most credible sources on each (link them).
3. The most common misconceptions and what's actually true.
4. What an expert in this area would tell me if I had 30 minutes with them.
5. The 5 questions I should be asking next.

Save the result as research-[topic-slug].md to my Drive at /Claude Research/.
```

**Output:** A structured research file in your Drive, with citations, ready to share or reuse.

**Try this next:** Ask Claude to summarise it as a 60-second briefing for a stakeholder.

---

## 2. Inbox triage at 9am

**Use it when:** You sit down to your inbox and there are 60+ unread emails.

**The prompt:**
```
Read all unread emails in my inbox from the last 24 hours. For each, tell me:
- Sender + subject (just enough so I know which one).
- Bucket: REPLY-TODAY / REPLY-THIS-WEEK / FYI-NO-ACTION / IGNORE-OR-UNSUBSCRIBE.
- If REPLY-TODAY, draft a 2-sentence reply in my voice.

Group output by bucket. Show me REPLY-TODAY first.
```

**Output:** Ordered triage with reply drafts. You skim, approve, and send.

**Try this next:** Ask Claude to schedule the REPLY-THIS-WEEK ones as Google Calendar tasks.

---

## 3. Meeting prep, 15 minutes before

**Use it when:** A meeting is 15 minutes away and you haven't prepped.

**The prompt:**
```
I have a meeting with [PERSON] at [TIME] about [TOPIC]. Pull from:
- Past emails with this person.
- Calendar events that mention them.
- Any Drive docs that mention them or the topic.

Give me:
1. The 3 most relevant facts I should remember.
2. The 2 questions I should ask.
3. Anything they're likely to ask me, and the 1-line answer I should be ready with.
```

**Output:** A 5-bullet briefing.

**Try this next:** "Now draft the follow-up email I should send after the meeting."

---

## 4. Drive cleanup, gently

**Use it when:** Your Drive root looks like a dumping ground.

**The prompt:**
```
Look at the top 50 files in the root of my Google Drive. For each:
- One-sentence summary.
- Suggested folder (existing or new).
- Whether it looks important, routine, or stale.

Don't move anything yet — just give me a table. I'll approve in batches.
```

**Output:** A table you can approve in 10 minutes.

**Try this next:** "Move the routine ones into the folders you suggested."

---

## 5. Weekly summary at 5pm Friday

**Use it when:** You want a recap of your own week without writing one.

**The prompt:**
```
Pull from my Gmail (sent + received), Calendar (events I attended), and Drive (files I created or edited) for the past 7 days. Give me:
1. Top 3 things I shipped or progressed.
2. Top 3 unresolved threads I should close next week.
3. One thing that took more time than it should have, and why.
4. A 2-sentence personal note I could send to my manager / partner / accountability buddy.
```

**Output:** A friction-free weekly review.

**Try this next:** Schedule this as a recurring task every Friday at 5pm.

---

## 6. Schedule a recurring task

**Use it when:** You've found one of these prompts that works and you want it run automatically.

**The prompt:**
```
Run [prompt from above] every [day/week] at [time]. Send the output to me via email at [your-email].
```

**Output:** Confirmation that the schedule is set. You'll get the output in your inbox.

**Try this next:** Tweak the schedule when you've seen 2–3 runs.

---

## 7. Draft a hard reply

**Use it when:** You owe someone a no, a pushback, or a clarification that you've been putting off.

**The prompt:**
```
I need to reply to [PERSON] about [SUBJECT]. The honest answer is [WHAT YOU ACTUALLY WANT TO SAY, blunt is fine].

Draft a reply in my voice that is:
- Kind but clear.
- 4 sentences max.
- Doesn't open new loops I'll regret.
- Leaves the door open if it should, closed if it shouldn't.
```

**Output:** A draft. You'll edit one line and send.

**Try this next:** Keep the prompt as your "hard reply" macro and reuse it.

---

## 8. Find the doc I half-remember

**Use it when:** You know you wrote it but can't find it.

**The prompt:**
```
Search my Drive and Gmail for anything I wrote or shared in the last 60 days about [VAGUE TOPIC]. Show me the top 5 candidates with one-line summaries. If you find the exact one I'm probably looking for based on [CLUE], say so.
```

**Output:** Fast retrieval that beats Drive's own search.

**Try this next:** Ask Claude to draft a follow-up email referencing the doc.

---

## 9. Calendar reality check

**Use it when:** Monday morning, you want to know what kind of week you're walking into.

**The prompt:**
```
Look at my calendar for the next 7 days. Tell me:
1. Total meeting hours per day.
2. Days that are over 60% meetings (red flag).
3. Any meetings that look like they could be a Slack message.
4. Any meetings I should prep for now while I have time.
5. Where there's a clear 2-hour block for deep work — propose moving one meeting if there isn't.
```

**Output:** A diagnosis of your week, not just a list.

**Try this next:** Approve the move and ask Claude to draft the rescheduling email.

---

## 10. Build a knowledge base for a topic

**Use it when:** You want Claude to "remember" a domain you keep working on.

**The prompt:**
```
Read everything in my Drive folder /Knowledge/[TOPIC]/ and Gmail threads tagged [TOPIC]. Summarise:
- The top 10 facts that matter.
- The 3 people who keep coming up.
- The decisions I've already made (so I don't relitigate them).

Save as knowledge-[topic-slug].md and auto-load it when I ask about this topic.
```

**Output:** A persistent context file Claude pulls from going forward.

**Try this next:** Update the file at the end of each project.

---

**Generated with Claude. Reviewed by Haojun Yong (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
