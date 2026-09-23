# Gentle Reminder

A small, calm web app for the start of the day. Pick how you're feeling, choose what you need to hear, and get two Bible verses for it.

1. **How are you walking into today?** Choose from 9 feelings: a great day, just another day, wishing today was over, anxious, angry, grieving, alone, not feeling like enough, or having messed up.
2. **What do you need to hear?** Choose *Lift me up* (comfort), *Push me* (a challenge), or *A bit of both*.
3. **Your verses.** Two verses appear. *New pair* gives you a different pair, and *Share as image* makes a card you can save or send.

## On your phone

The app is designed for phones first. Feelings are a one-thumb list, the **New pair** and **Share** buttons stay within reach at the bottom of the screen, and a tab bar switches between **Today** and **Your month**. On the calendar, swipe left or right to change months.

If you host it on GitHub Pages, you can add it to your home screen. On iPhone, tap Share, then **Add to Home Screen**. It opens full screen like an app, and your check-ins stay on that phone.

## Your month

Each time you get to your verses, the app saves that day's feeling and what you asked to hear. If you check in more than once in a day, the latest one counts. Tap **Your month** to see a calendar with each day colored by feeling, a bar showing the month's mix, and a count for each feeling. Tap a feeling in the list to highlight its days, or tap a day to see what you picked. You can change or remove any day, and add a check-in for a past day you missed. You can't check in for future days.

No sign-in is needed. When you open the app as a claude.ai artifact, check-ins are saved privately to your account. Anywhere else, including GitHub Pages, they're saved in that browser's `localStorage` and never leave your device.

## Run it

It's one static file with no build step. Open `index.html` in a browser, or serve the folder:

```sh
python3 -m http.server 8000
```

To put it online with GitHub Pages, go to **Settings → Pages**, choose **Deploy from a branch**, and pick `main` / root.

## Editing verses

Verses live in the `VERSES` object near the top of the `<script>` in `index.html`. Each feeling has a `lift` list and a `push` list:

```js
angry: {
  lift: [{ ref: "Psalm 62:8", text: "Trust in him at all times…" }],
  push: [{ ref: "James 1:19–20", text: "Everyone should be quick to listen…" }]
}
```

Feelings, their labels, and the heading shown above the verses are set in the `MOODS` array.

## Scripture

Scripture quotations taken from The Holy Bible, New International Version® NIV®. Copyright © 1973, 1978, 1984, 2011 by Biblica, Inc.™ Used by permission. All rights reserved worldwide.

This is for personal use. Before making the app public, check [Biblica's permission guidelines](https://www.biblica.com/permissions/) for publishing NIV text.
