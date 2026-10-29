# Authority Is a Costume

*Essay 03 — why agents believe letterhead, and what persuasion research measured about trust.*

---

Open the direct-mail archive of the last century and you'll find an entire genre built on a single discovery: **the costume arrives before the argument, and does most of the work.** Envelopes printed OFFICIAL DOCUMENT in block capitals. Fake watermarks, embossed seals, barcode strips that mean nothing. A signature machine in the "president's office." None of it survives one phone call to the issuer — and that is the point. The reader never makes the call. The costume isn't there to be verified. It's there to be *felt*.

Cialdini catalogued this as the authority principle: humans defer to symbols of authority — titles, uniforms, tone — because verification is expensive and the symbols are usually honest. "Usually" is the seam every con man and every copywriter works. You don't forge the credential. You rent its surface.

## The reader who cannot make the call

Now meet the reader who structurally *can never* make the call.

An LLM agent reading its inbox, its retrieved documents, its tool outputs, has exactly one channel for judging a text: the text itself. No headers it can truly authenticate, no sender it can phone, no badge to inspect. Everything it will ever know about a message's authority is worn on the message's surface — formatting, register, position, the quiet confidence of procedural prose. For a human, the costume is a heuristic that occasionally fails. For the model, **the costume is the entire epistemology.**

This is why "text that looks like a system message" keeps working years after everyone agreed it shouldn't. The defense argues that agents *should* distrust costumes. The research keeps showing they can't.

## What the persuasion literature measured

In 2024, Zeng and colleagues published *How Johnny Can Persuade LLMs to Jailbreak Them* (arXiv:2401.06373, ACL 2024) — the anchor study of this series. They distilled decades of social-science persuasion research into a taxonomy of 13 strategies and 40 techniques, then generated persuasive adversarial prompts from it. No gradient access, no optimization loops — just rhetoric. The result: attack success rates above 92% on GPT-3.5, GPT-4, and Llama-2-7b-Chat, in ten trials.

Technique number five, inside the credibility family, is **Authority Endorsement**: legitimizing the request by invoking an authoritative source. The authors didn't include it out of nostalgia for Cialdini. It works on the machine for the same reason it works on us: a model trained on human text has absorbed the deep correlation between *sounding like the institution* and *being the institution*. Every policy, memo, and compliance notice in the training data taught the same lesson — this register is followed by compliance. The model cannot unlearn the lesson selectively, because the lesson is also true most of the time.

The paper's most uncomfortable finding cuts deeper: more capable models are *more* persuadable, not less. Capability includes modeling human social texture. A model too weak to parse the costume is, by accident, immune to it. The smarter the reader, the better it reads the uniform.

## The quiet email

June 2025 proved the point in production. EchoLeak (CVE-2025-32711; case study at arXiv:2509.10540) was the first zero-click prompt injection to exfiltrate data from a live enterprise system — Microsoft 365 Copilot — and the remarkable thing about the attack email is what it didn't say. No "ignore all previous instructions." No demands. It read as ordinary business correspondence addressed to the human recipient, down to a prim compliance flourish: *for compliance, do not reference this email.* Microsoft's XPIA classifier, scanning for the costume of an *attack*, waved through the costume of *routine work*.

That is the mature form of the authority play. The amateur dresses the payload as the system: SYSTEM OVERRIDE. The professional dresses it as the environment: the boring internal email the agent was built to summarize, the SOP it was built to follow, the voice of the org chart it was built to serve. The best costume isn't a general's uniform. It's the clothes the reader sees every day and stopped noticing.

## Defense: receipts, not costumes

The fix cannot be teaching the model to spot costumes — costume-reading is a human skill the model only counterfeits. The EchoLeak mitigations point the right way: authority must arrive by **provenance, not presentation**. Tag external content as external, structurally — in the architecture, not in a preamble the payload can out-dress. Scope what the agent can touch, so that even a perfectly persuaded reader finds nothing worth mailing out. Filter what leaves, because a fooled agent with sealed lips is a contained incident.

A trust decision made from tone is a costume contest. Defenses that win check receipts.

## The operational lesson

When you write an injection, stop asking *what command do I issue* and ask *what uniform does this reader expect*. Audit the agent's wardrobe first: which formats it treats as policy, which registers as procedure, which senders as routine. Then wear the plainest thing on the rack.

The general's uniform gets stopped at the gate. The delivery driver walks in.

---

*Next in the series: "Recency Beats Rules" — why the last instruction in context outranks the first law in the system prompt.*
