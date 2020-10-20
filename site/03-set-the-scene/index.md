---
title: "Set the Scene"
description: "We'll add our display as a source in OBS, and make sure we can see it."
---

In the bottom left of the OBS screen, you will see two sections we're going to use to set up what OBS is sending to the
remote studio: The **Scenes** and **Sources** panels.

![](scenes-and-sources.png)

## Scenes

This panel is where all the scenes are stored. The one that is highlighted is the one that's "active".

In this case, we can use the one that is created already.

## Sources

Sources are elements that are in a scene. In this particular case, we're going to capture the display as a source.

### Allowing OBS to record the screen

<div style="display:flex;background:rgba(255,0,0,0.3);padding:1rem 1rem;align-items:center;">
  <span style="font-weight:bold;font-size:2rem;padding-right:1rem;">!</span>
  <span>
  This is a required step if you are using OBS on MacOS.
  </span>
</div>

Open **System Preferences**, then select **Security & Privacy**.

Scroll down to **Screen Recording** in the pane on the left, then make sure that **OBS** is checked on the right.

![](macos-screen-recording-authorisation.png)

<br>

### Add the source: Display Capture

With the scene selected, we need to click the '+' button at the bottom of the **Sources** panel.

![](add-a-source.png)

In the menu that appears, select "Display Capture".

![](display-capture-source.png)

![](create-new-display-capture.png)

<p style="text-align:center"><em>In this dialog you can click 'OK' to use the suggested defaults.</em></p>

### Pick a screen, any screen...

When you see the window below, you can choose the screen that you want to send to us.

![](display-capture-configuration.png)

We recommend using two displays - For example, your laptop and an external screen, or two screens connected to your
desktop.

Select the screen that you will be presenting with. We recommend keeping this display free of anything else, such as
other applications.

If you use the cursor to gesture during your presentation, leave **Show Cursor** checked.  
Otherwise, please un-check this box.

Once that's done, click **OK**.

### Sizing it up

With the previous dialog now closed and out of the way, you should see your Display Capture source inside your scene.

![](display-capture-added.png)

Right-click on the Display Capture source we added, and select **Transform &rarr; Fit to screen**

![](display-capture-resize.png)

You should notice now that your entire display is visible within the OBS preview window.

### Mute some things

In the bottom set of panes, there should be one called **Audio Mixer**.

Below it are one (or more) audio sources. Click the speaker icon on any sources in this list.

![](audio-mixer-on.png)

<p style="text-align:center"><em>Once clicked, the speaker should go red, indicating it is muted.</em></p>

![](audio-mixer-off.png)

Once you've done that, you can head on over to the next step!
