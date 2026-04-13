<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Email Marketing</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600;700&family=Manrope:wght@400;500;700;800&display=swap" rel="stylesheet">
  <style>
    :root {
      --panel: rgba(248, 239, 221, 0.96);
      --panel-soft: rgba(255, 248, 234, 0.86);
      --text: #2e1a40;
      --muted: #66507b;
      --purple: #71419b;
      --purple-deep: #29123f;
      --gold: #d7b15c;
      --red: #b43b4d;
      --green: #368856;
      --line: rgba(113, 65, 155, 0.15);
      --shadow: 0 24px 60px rgba(8, 2, 15, 0.35);
      --radius: 28px;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }

    body {
      margin: 0;
      font-family: "Manrope", sans-serif;
      background:
        radial-gradient(circle at top left, rgba(215, 177, 92, 0.12), transparent 22%),
        radial-gradient(circle at 85% 15%, rgba(113, 65, 155, 0.24), transparent 24%),
        linear-gradient(160deg, #0f0618 0%, #1c0c2c 38%, #30124b 72%, #12081d 100%);
      color: #f9f0dc;
      line-height: 1.6;
      min-height: 100vh;
    }

    .page {
      width: min(1180px, calc(100% - 32px));
      margin: 0 auto;
      padding: 28px 0 56px;
    }

    .hero {
      position: relative;
      overflow: hidden;
      padding: 56px 42px;
      border-radius: 0 0 34px 34px;
      background: linear-gradient(140deg, #160920 0%, #341552 34%, #71419b 70%, #d7b15c 100%);
      box-shadow: var(--shadow);
      isolation: isolate;
    }

    .hero::before,
    .hero::after {
      content: "";
      position: absolute;
      border-radius: 50%;
      background: rgba(255,255,255,0.08);
      filter: blur(2px);
      z-index: -1;
    }

    .hero::before {
      width: 260px;
      height: 260px;
      top: -100px;
      right: -60px;
    }

    .hero::after {
      width: 180px;
      height: 180px;
      bottom: -60px;
      left: 10px;
    }

    .eyebrow,
    .section-label,
    .pill {
      display: inline-flex;
      align-items: center;
      padding: 7px 14px;
      border-radius: 999px;
      font-size: 11px;
      font-weight: 800;
      letter-spacing: 0.12em;
      text-transform: uppercase;
    }

    .eyebrow {
      background: rgba(255,255,255,0.14);
      border: 1px solid rgba(255,255,255,0.22);
      color: #fff5dd;
    }

    .section-label {
      background: rgba(215, 177, 92, 0.16);
      color: var(--purple);
      margin-bottom: 14px;
    }

    .pill {
      background: rgba(113, 65, 155, 0.1);
      color: var(--purple-deep);
      margin: 0 6px 8px 0;
      letter-spacing: 0.08em;
    }

    h1, h2, h3 {
      margin: 0;
      font-family: "Cinzel", serif;
      font-weight: 700;
      letter-spacing: 0.02em;
    }

    h1 {
      margin-top: 18px;
      font-size: clamp(2.6rem, 7vw, 5rem);
      line-height: 0.96;
      max-width: 11ch;
    }

    .hero p {
      max-width: 72ch;
      margin: 18px 0 0;
      font-size: 1.04rem;
      color: rgba(255, 248, 235, 0.92);
    }

    .hero-grid,
    .grid-2,
    .grid-3,
    .grid-4 {
      display: grid;
      gap: 16px;
      margin-top: 18px;
    }

    .hero-grid {
      grid-template-columns: repeat(4, minmax(0, 1fr));
      margin-top: 28px;
    }

    .grid-2 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
    .grid-3 { grid-template-columns: repeat(3, minmax(0, 1fr)); }
    .grid-4 { grid-template-columns: repeat(4, minmax(0, 1fr)); }

    .hero-stat {
      padding: 16px;
      border-radius: 18px;
      background: rgba(255,255,255,0.12);
      border: 1px solid rgba(255,255,255,0.16);
      backdrop-filter: blur(8px);
    }

    .hero-stat strong {
      display: block;
      font-size: 1.2rem;
      margin-bottom: 4px;
      color: #fff5dd;
    }

    .section,
    .cta {
      margin-top: 18px;
      padding: 28px;
      background: var(--panel);
      color: var(--text);
      box-shadow: var(--shadow);
      border-radius: var(--radius);
      border: 1px solid rgba(255,255,255,0.28);
    }

    .section h2 {
      font-size: clamp(1.8rem, 4vw, 2.7rem);
      line-height: 1.02;
      margin-bottom: 12px;
    }

    .section p {
      margin: 0 0 14px;
      color: var(--muted);
    }

    .card,
    .lesson-card,
    .template-card,
    .warning-card {
      background: var(--panel-soft);
      border: 1px solid var(--line);
      border-radius: 22px;
      padding: 18px;
    }

    .lesson-card { border-top: 4px solid var(--purple); }
    .warning-card { border-top: 4px solid var(--red); }
    .template-card { border-top: 4px solid var(--green); }

    .card h3,
    .lesson-card h3,
    .template-card h3,
    .warning-card h3 {
      font-size: 1.08rem;
      color: var(--purple-deep);
      margin-bottom: 8px;
    }

    ul,
    ol {
      margin: 0;
      padding-left: 20px;
      color: var(--muted);
    }

    li { margin-bottom: 8px; }

    code,
    pre {
      font-family: Consolas, "Courier New", monospace;
    }

    pre {
      white-space: pre-wrap;
      margin: 12px 0 0;
      padding: 14px;
      border-radius: 16px;
      background: rgba(41, 18, 63, 0.08);
      border: 1px solid rgba(113, 65, 155, 0.12);
      color: var(--purple-deep);
      font-weight: 700;
    }

    a {
      color: var(--purple-deep);
      font-weight: 800;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 18px;
      overflow: hidden;
      border-radius: 18px;
      background: rgba(255, 248, 234, 0.72);
    }

    th,
    td {
      padding: 13px 14px;
      text-align: left;
      border-bottom: 1px solid var(--line);
      vertical-align: top;
      color: var(--muted);
      font-size: 0.95rem;
    }

    th {
      color: var(--purple-deep);
      background: rgba(215, 177, 92, 0.18);
      font-weight: 800;
    }

    tr:last-child td { border-bottom: 0; }

    .quote {
      padding: 18px;
      margin-top: 18px;
      border-radius: 22px;
      background: linear-gradient(135deg, rgba(215, 177, 92, 0.18), rgba(113, 65, 155, 0.08));
      border: 1px solid rgba(215, 177, 92, 0.22);
      color: var(--purple-deep);
      font-weight: 700;
    }

    .cta {
      text-align: center;
      background: linear-gradient(135deg, rgba(41, 18, 63, 0.98), rgba(113, 65, 155, 0.92));
      color: #fff4de;
    }

    .cta h2 {
      font-size: clamp(1.9rem, 4vw, 3rem);
      margin-bottom: 12px;
    }

    .cta p {
      max-width: 66ch;
      margin: 0 auto;
      color: rgba(255, 243, 221, 0.88);
    }

    @media (max-width: 980px) {
      .hero-grid,
      .grid-2,
      .grid-3,
      .grid-4 {
        grid-template-columns: 1fr;
      }

      table,
      thead,
      tbody,
      th,
      td,
      tr {
        display: block;
      }

      th { display: none; }

      td {
        border-bottom: 0;
        padding: 10px 14px;
      }

      tr {
        border-bottom: 1px solid var(--line);
        padding: 8px 0;
      }
    }

    @media (max-width: 640px) {
      .page {
        width: min(100% - 16px, 1180px);
      }

      .hero,
      .section,
      .cta {
        padding: 22px;
      }
    }
  </style>
</head>
<body>
  <div class="page">
    <section class="hero">
      <span class="eyebrow">Module 5</span>
      <h1>Email Marketing</h1>
      <p>Build an audience you own. Learn how to create a lead magnet, collect subscribers, send a welcome sequence, write weekly emails, segment your list, track performance, and use AI without sounding generic.</p>
      <div class="hero-grid">
        <div class="hero-stat">
          <strong>Grow</strong>
          <span>Turn followers, viewers, and store visitors into email subscribers</span>
        </div>
        <div class="hero-stat">
          <strong>Nurture</strong>
          <span>Use welcome emails and newsletters to build trust over time</span>
        </div>
        <div class="hero-stat">
          <strong>Sell</strong>
          <span>Promote offers without depending only on social algorithms</span>
        </div>
        <div class="hero-stat">
          <strong>Track</strong>
          <span>Use clicks, replies, purchases, and unsubscribes to improve your emails</span>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="section-label">Why It Matters</div>
      <h2>Your Email List Is Owned Attention</h2>
      <p>Social platforms are powerful, but the algorithm decides who sees your content. Email gives students a direct way to reach people who already raised their hand and asked for more.</p>
      <div class="quote">The goal is not to collect random emails. The goal is to build a list of people who care about the problem you solve.</div>
    </section>

    <section class="section">
      <div class="section-label">Module Promise</div>
      <h2>What Students Will Learn</h2>
      <div class="grid-3">
        <div class="card">
          <h3>Email Foundation</h3>
          <p>Students learn the difference between a follower, lead, subscriber, buyer, and repeat customer.</p>
        </div>
        <div class="card">
          <h3>Lead Magnets</h3>
          <p>Students learn how to create a free resource that attracts the right audience instead of a random list.</p>
        </div>
        <div class="card">
          <h3>Opt-In Pages</h3>
          <p>Students learn how landing pages and forms collect subscribers and trigger delivery emails.</p>
        </div>
        <div class="card">
          <h3>Welcome Sequences</h3>
          <p>Students learn how to introduce themselves, deliver value, build trust, and invite subscribers to the next step.</p>
        </div>
        <div class="card">
          <h3>Newsletters</h3>
          <p>Students learn a simple weekly email format they can repeat without overthinking.</p>
        </div>
        <div class="card">
          <h3>Segmentation</h3>
          <p>Students learn how to send more relevant emails based on interests, clicks, purchases, and subscriber stage.</p>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="section-label">Lesson Plan</div>
      <h2>Full Module Outline</h2>
      <div class="grid-2">
        <div class="lesson-card">
          <span class="pill">Lesson 1</span>
          <h3>Email Marketing Basics</h3>
          <p>Email marketing is the process of building a permission-based list and sending useful messages that educate, connect, and guide people toward the next step.</p>
          <p>Students should understand that email is not just for selling. It is for relationship building, trust, delivery, follow-up, product launches, customer education, and repeat sales.</p>
          <ul>
            <li>Follower: someone who sees content on a platform.</li>
            <li>Lead: someone who showed interest.</li>
            <li>Subscriber: someone who gave permission to be emailed.</li>
            <li>Buyer: someone who purchased.</li>
            <li>Repeat customer: someone who trusts the brand enough to buy again.</li>
          </ul>
          <div class="quote">Student task: write one sentence explaining why someone should join your email list.</div>
        </div>

        <div class="lesson-card">
          <span class="pill">Lesson 2</span>
          <h3>Choosing an Email Platform</h3>
          <p>Students need an email service provider, not a personal Gmail account. A real platform gives them forms, landing pages, automations, unsubscribe links, analytics, and compliant sending tools.</p>
          <ul>
            <li>Mailchimp is beginner-friendly for newsletters, forms, audiences, and campaign reporting.</li>
            <li>Kit, formerly ConvertKit, is strong for creators, landing pages, tags, sequences, and visual automations.</li>
            <li>Stan, Beacons, Shopify, and other tools may connect to email platforms or collect buyer emails.</li>
            <li>Choose based on ease, budget, automations, tagging, forms, and product integrations.</li>
          </ul>
          <div class="quote">Decision shortcut: if you are a creator building funnels and sequences, Kit is a strong fit. If you want a simple newsletter and reports, Mailchimp can work well.</div>
        </div>

        <div class="lesson-card">
          <span class="pill">Lesson 3</span>
          <h3>Create a Lead Magnet</h3>
          <p>A lead magnet is a free resource people receive in exchange for joining the email list. It should solve a small, specific problem quickly.</p>
          <p>The best lead magnets are not huge. They are useful, focused, and connected to the paid offer students eventually want to sell.</p>
          <ul>
            <li>Checklist.</li>
            <li>Prompt pack.</li>
            <li>Mini guide.</li>
            <li>Swipe file.</li>
            <li>Template.</li>
            <li>Calculator or tracker.</li>
            <li>Free training or private video.</li>
          </ul>
          <div class="quote">Example: If the paid offer is a Canva template pack, the lead magnet could be "10 Post Ideas for Your First Digital Product Launch."</div>
        </div>

        <div class="lesson-card">
          <span class="pill">Lesson 4</span>
          <h3>Build the Opt-In Page</h3>
          <p>The opt-in page should make one promise and ask for one action. Do not overload it with too many links, products, or explanations.</p>
          <ul>
            <li>Clear headline: what they get.</li>
            <li>Short description: who it helps and why it matters.</li>
            <li>Simple form: first name and email is enough for beginners.</li>
            <li>Strong button: "Send Me the Checklist" is better than "Submit."</li>
            <li>Privacy note: tell people they can unsubscribe.</li>
            <li>Thank-you page or success message: tell them what happens next.</li>
          </ul>
          <div class="quote">Student task: create one landing page or form for one lead magnet before building multiple funnels.</div>
        </div>

        <div class="lesson-card">
          <span class="pill">Lesson 5</span>
          <h3>The 5-Email Welcome Sequence</h3>
          <p>The welcome sequence is the first relationship builder. It should deliver the lead magnet, introduce the creator, provide quick wins, build trust, and make a simple offer.</p>
          <ul>
            <li>Email 1: deliver the free resource and set expectations.</li>
            <li>Email 2: introduce your story and who you help.</li>
            <li>Email 3: teach one useful tip connected to the lead magnet.</li>
            <li>Email 4: handle a common mistake or objection.</li>
            <li>Email 5: invite subscribers to the next step or paid offer.</li>
          </ul>
          <div class="quote">Timing: send Email 1 immediately, then space the rest over 5 to 10 days so subscribers do not feel overwhelmed.</div>
        </div>

        <div class="lesson-card">
          <span class="pill">Lesson 6</span>
          <h3>Weekly Newsletter Formula</h3>
          <p>A newsletter does not have to be fancy. It just needs to show up consistently with value that matches the audience's goals.</p>
          <ul>
            <li>Hook: one sentence that names the problem or lesson.</li>
            <li>Story or context: why this matters right now.</li>
            <li>Teaching point: one helpful idea, step, or example.</li>
            <li>Action: one thing the reader can try.</li>
            <li>CTA: reply, click, watch, download, or buy.</li>
          </ul>
          <div class="quote">Simple rhythm: one weekly value email plus launch emails only when there is something clear to promote.</div>
        </div>

        <div class="lesson-card">
          <span class="pill">Lesson 7</span>
          <h3>Segmentation and Tags</h3>
          <p>Segmentation means dividing the list into groups so people receive emails that match their interests or actions.</p>
          <p>Students do not need complicated segmentation at first. Start with a few useful tags that make future emails more relevant.</p>
          <ul>
            <li>Lead magnet downloaded.</li>
            <li>Clicked product link.</li>
            <li>Purchased product.</li>
            <li>Interested in AI tools.</li>
            <li>Interested in digital products.</li>
            <li>Interested in coaching or services.</li>
          </ul>
          <div class="quote">Rule: send more specific emails to people who have shown specific interest.</div>
        </div>

        <div class="lesson-card">
          <span class="pill">Lesson 8</span>
          <h3>Using AI to Write Emails</h3>
          <p>AI can help brainstorm, outline, rewrite, and repurpose emails. Students should still add their voice, examples, real stories, and truthful claims.</p>
          <ul>
            <li>Use AI to create subject line options.</li>
            <li>Use AI to turn a TikTok script into an email.</li>
            <li>Use AI to outline a 5-email sequence.</li>
            <li>Use AI to simplify or improve clarity.</li>
            <li>Do not let AI invent testimonials, income proof, or false customer stories.</li>
          </ul>
          <div class="quote">Best prompt: "Write this in my voice, keep it simple, make it helpful, and avoid exaggerated claims."</div>
        </div>

        <div class="lesson-card">
          <span class="pill">Lesson 9</span>
          <h3>Email Compliance Basics</h3>
          <p>Students should only email people who gave permission, and they should make it easy for people to unsubscribe.</p>
          <ul>
            <li>Do not buy email lists.</li>
            <li>Do not use misleading subject lines.</li>
            <li>Identify the message as an ad when required.</li>
            <li>Include a valid physical postal address or business mailing address.</li>
            <li>Include a working unsubscribe link.</li>
            <li>Honor unsubscribe requests quickly.</li>
          </ul>
          <div class="quote">This is another reason to use a real email platform: it helps manage unsubscribe links and list compliance.</div>
        </div>

        <div class="lesson-card">
          <span class="pill">Lesson 10</span>
          <h3>Track and Improve Your Emails</h3>
          <p>Email data helps students improve. Open rates can be useful, but privacy tools can make opens less exact. Clicks, replies, purchases, unsubscribes, and list growth give stronger signals.</p>
          <ul>
            <li>Open rate: subject line and list interest signal, but not perfectly accurate.</li>
            <li>Click rate: how many people clicked a link.</li>
            <li>Reply rate: how many people engaged directly.</li>
            <li>Unsubscribe rate: whether the content is mismatched or too frequent.</li>
            <li>Conversion rate: how many people took the desired action.</li>
          </ul>
          <div class="quote">Simple test: change one thing at a time, like the subject line, CTA, offer, or email length.</div>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="section-label">Welcome Sequence</div>
      <h2>5-Email Sequence Template</h2>
      <table>
        <thead>
          <tr>
            <th>Email</th>
            <th>Goal</th>
            <th>Simple Subject Line</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Email 1</td>
            <td>Deliver the lead magnet and tell them what to expect next.</td>
            <td>Here is your [resource name]</td>
          </tr>
          <tr>
            <td>Email 2</td>
            <td>Introduce who you help, your story, and why this topic matters.</td>
            <td>Before you start, read this</td>
          </tr>
          <tr>
            <td>Email 3</td>
            <td>Teach one quick win that helps them use the free resource.</td>
            <td>One simple way to use this today</td>
          </tr>
          <tr>
            <td>Email 4</td>
            <td>Address the biggest mistake or objection that keeps people stuck.</td>
            <td>The mistake most beginners make</td>
          </tr>
          <tr>
            <td>Email 5</td>
            <td>Invite them to buy, book, watch, join, or take the next step.</td>
            <td>Your next step</td>
          </tr>
        </tbody>
      </table>
    </section>

    <section class="section">
      <div class="section-label">Lead Magnet Ideas</div>
      <h2>Creator Plug Lead Magnet Bank</h2>
      <div class="grid-3">
        <div class="template-card"><h3>Digital Product Sellers</h3><p>Free checklist: "7 Things to Fix Before You Launch Your First Digital Product."</p></div>
        <div class="template-card"><h3>AI Creators</h3><p>Prompt pack: "25 AI Prompts for Faster Content, Product Ideas, and Captions."</p></div>
        <div class="template-card"><h3>TikTok Creators</h3><p>Swipe file: "30 TikTok Hook Ideas for Beginners."</p></div>
        <div class="template-card"><h3>Store Setup</h3><p>Checklist: "Creator Store Setup Checklist Before You Add Your Link in Bio."</p></div>
        <div class="template-card"><h3>MRR / PLR Sellers</h3><p>Worksheet: "MRR/PLR License Review Checklist."</p></div>
        <div class="template-card"><h3>Content Planning</h3><p>Planner: "7-Day Content Plan for Your First Offer."</p></div>
      </div>
    </section>

    <section class="section">
      <div class="section-label">Templates</div>
      <h2>Copy and Paste Swipe File</h2>
      <div class="grid-2">
        <div class="template-card">
          <h3>Opt-In Page Copy</h3>
          <pre>Get the free [resource name] and learn how to [specific result] without [common frustration]. Enter your email and I will send it to you.</pre>
        </div>
        <div class="template-card">
          <h3>Delivery Email</h3>
          <pre>Subject: Here is your [resource name]

Hi [Name],

Here is the free resource I promised: [link]

Start with page one, then pick one action to complete today. I will send you a few more tips this week to help you use it.</pre>
        </div>
        <div class="template-card">
          <h3>Weekly Newsletter</h3>
          <pre>Subject: [specific lesson or problem]

Here is something I want you to remember:

[One helpful lesson]

Why it matters:
[Short explanation]

Try this:
[Simple action]

Next step:
[CTA]</pre>
        </div>
        <div class="template-card">
          <h3>Simple Sales Email</h3>
          <pre>Subject: If you want help with [problem]

If you are trying to [goal], I made [offer name] to help you [specific result].

Inside, you get:
- [Benefit 1]
- [Benefit 2]
- [Benefit 3]

You can grab it here: [link]</pre>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="section-label">Checklists</div>
      <h2>Student Downloads to Include</h2>
      <div class="grid-2">
        <div class="template-card">
          <h3>Email Setup Checklist</h3>
          <ol>
            <li>Choose an email platform.</li>
            <li>Create one lead magnet.</li>
            <li>Create one form or landing page.</li>
            <li>Write the thank-you message.</li>
            <li>Write Email 1 to deliver the resource.</li>
            <li>Write the full 5-email welcome sequence.</li>
            <li>Add unsubscribe and mailing address details through the platform.</li>
            <li>Test the form, delivery email, and links.</li>
          </ol>
        </div>
        <div class="template-card">
          <h3>Before You Send Checklist</h3>
          <ol>
            <li>Is the subject line clear?</li>
            <li>Is the email useful or relevant?</li>
            <li>Is there one main CTA?</li>
            <li>Do all links work?</li>
            <li>Is the email truthful and not exaggerated?</li>
            <li>Is the unsubscribe link included?</li>
            <li>Does the email match the audience segment?</li>
            <li>Would you want to receive this email?</li>
          </ol>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="section-label">Common Mistakes</div>
      <h2>What Students Should Avoid</h2>
      <div class="grid-3">
        <div class="warning-card">
          <h3>Buying Email Lists</h3>
          <p>Purchased lists usually create spam complaints, low trust, bad deliverability, and compliance risk.</p>
        </div>
        <div class="warning-card">
          <h3>Only Selling</h3>
          <p>If every email is a pitch, subscribers stop trusting the list. Mix education, story, proof, and offers.</p>
        </div>
        <div class="warning-card">
          <h3>No Welcome Sequence</h3>
          <p>New subscribers are most interested right after they join. Do not waste that moment.</p>
        </div>
        <div class="warning-card">
          <h3>Too Many CTAs</h3>
          <p>One email should usually have one main action. Too many links can confuse the reader.</p>
        </div>
        <div class="warning-card">
          <h3>Ignoring Clicks</h3>
          <p>Open rates can be inflated by privacy tools. Clicks and replies show stronger engagement.</p>
        </div>
        <div class="warning-card">
          <h3>Sounding Like AI</h3>
          <p>AI drafts need human stories, examples, and brand voice before sending.</p>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="section-label">Knowledge Check</div>
      <h2>Quick Student Quiz</h2>
      <div class="grid-2">
        <div class="card">
          <h3>Question 1</h3>
          <p>What is the main purpose of a lead magnet?</p>
          <div class="quote">Answer: To give a useful free resource in exchange for permission to email someone.</div>
        </div>
        <div class="card">
          <h3>Question 2</h3>
          <p>What should Email 1 in a welcome sequence do?</p>
          <div class="quote">Answer: Deliver the promised resource and set expectations for what comes next.</div>
        </div>
        <div class="card">
          <h3>Question 3</h3>
          <p>Why is segmentation useful?</p>
          <div class="quote">Answer: It helps send the right message to the right people based on interest or behavior.</div>
        </div>
        <div class="card">
          <h3>Question 4</h3>
          <p>Should students buy email lists to grow faster?</p>
          <div class="quote">Answer: No. Build a permission-based list with people who actually want the content.</div>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="section-label">Sources</div>
      <h2>Research Links</h2>
      <p>Use these as platform and compliance references when recording walkthroughs or updating student resources.</p>
      <ul>
        <li><a href="https://mailchimp.com/resources/email-marketing-strategy/">Mailchimp: Email Marketing Strategy</a></li>
        <li><a href="https://mailchimp.com/resources/email-sequence/">Mailchimp: Email Sequences</a></li>
        <li><a href="https://mailchimp.com/resources/email-marketing-benchmarks/">Mailchimp: Email Marketing Benchmarks</a></li>
        <li><a href="https://mailchimp.com/fr/help/about-open-and-click-rates/">Mailchimp: About Open and Click Rates</a></li>
        <li><a href="https://help.kit.com/en/articles/2502666-how-to-use-kit-visual-automations">Kit: Visual Automations</a></li>
        <li><a href="https://help.kit.com/en/articles/5523023-how-to-create-your-first-kit-visual-automation">Kit: Create Your First Visual Automation</a></li>
        <li><a href="https://kit.com/landing-pages">Kit: Landing Pages</a></li>
        <li><a href="https://www.ftc.gov/business-guidance/resources/can-spam-act-compliance-guide-business">FTC: CAN-SPAM Act Compliance Guide for Business</a></li>
      </ul>
    </section>

    <section class="cta">
      <h2>Build the List Before You Need It</h2>
      <p>Email turns attention into a relationship. Start with one useful lead magnet, one welcome sequence, and one weekly email that helps your audience take the next step.</p>
    </section>
  </div>
</body>
