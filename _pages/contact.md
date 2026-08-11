---
layout: page
title: Contact
permalink: /contact/
description: For research questions, collaboration ideas, or anything else, please feel free to reach out.
nav: true
nav_order: 3
---


<form id="contact-form" class="contact-form">
  <div class="contact-field">
    <label for="contact-name">Name</label>
    <input id="contact-name" name="name" type="text" autocomplete="name" required>
  </div>

  <div class="contact-field">
    <label for="contact-email">Email</label>
    <input id="contact-email" name="email" type="email" autocomplete="email" required>
  </div>

  <div class="contact-field">
    <label for="contact-message">Message</label>
    <textarea id="contact-message" name="message" rows="7" required></textarea>
  </div>

  <button type="submit" class="contact-submit">Send message</button>
  <p id="contact-status" class="contact-status" aria-live="polite"></p>
</form>

<p class="contact-fallback">
  You can also email me directly at
  <a href="mailto:ivytgliu@uw.edu">ivytg[MyLastName] "at" uw "dot" edu</a>.
</p>

<script>
  document.getElementById("contact-form").addEventListener("submit", function (event) {
    event.preventDefault();

    const form = event.currentTarget;
    const name = form.elements.name.value.trim();
    const email = form.elements.email.value.trim();
    const message = form.elements.message.value.trim();
    const subject = encodeURIComponent("Website message from " + name);
    const body = encodeURIComponent("Name: " + name + "\nEmail: " + email + "\n\nMessage:\n" + message);

    document.getElementById("contact-status").textContent =
      "Your email app should open with the message ready to send.";
    window.location.href = "mailto:ivytgliu@uw.edu?subject=" + subject + "&body=" + body;
  });
</script>

<style>
  .contact-form {
    margin-top: 1.5rem;
    max-width: 34rem;
  }

  .contact-field {
    margin-bottom: 1rem;
  }

  .contact-field label {
    display: block;
    font-weight: 500;
    margin-bottom: 0.35rem;
  }

  .contact-field input,
  .contact-field textarea {
    background: var(--global-bg-color);
    border: 1px solid var(--global-divider-color);
    border-radius: 0.35rem;
    color: var(--global-text-color);
    font: inherit;
    padding: 0.65rem 0.75rem;
    width: 100%;
  }

  .contact-field input:focus,
  .contact-field textarea:focus {
    border-color: var(--global-theme-color);
    outline: 2px solid color-mix(in srgb, var(--global-theme-color) 25%, transparent);
    outline-offset: 1px;
  }

  .contact-submit {
    background: var(--global-theme-color);
    border: 1px solid var(--global-theme-color);
    border-radius: 0.35rem;
    color: var(--global-hover-text-color);
    cursor: pointer;
    font: inherit;
    font-weight: 500;
    padding: 0.65rem 1rem;
  }

  .contact-submit:hover {
    background: var(--global-hover-color);
    border-color: var(--global-hover-color);
  }

  .contact-status,
  .contact-fallback {
    color: var(--global-text-color-light);
    font-size: 0.95rem;
    margin-top: 1rem;
  }
</style>
