# How to repair the Control Hub WiFi

## Incident Overview

### [March 20th Evening Study Session]

While the new freshmen (Class of '27) in the Programming and Electronics Division were happily transferring code, the Control Hub’s WiFi suddenly disconnected.

At this moment, no one realized the severity of the problem.

ZHZ left their computer, crossed half of the clubroom from the Programming and Electronics Division to the Engineering Division, and shouted before arriving: "Did you unplug the car’s power supply? I’m transferring code (>_<)"

The Programming and Electronics students immediately stopped what they were doing and gathered around the robot.

"No, the power supply is still connected, isn’t it? O_o"

"Huh? O_o"

ZHZ walked up to the robot and looked at the Control Hub. The yellow light blinking on the only colorful LED was flashing so rapidly.

"What’s this? O_o" ZHZ had never seen this indicator before.

A senior from the Engineering Division turned and said, "That blinks when the battery is low."

It suddenly dawned on me—I remembered seeing "6.73V" on the Driver Hub a few minutes ago.

At the time, I marveled at its wide input voltage range and didn’t give it much thought.

Now that I think about it, if I had realized the issue and unplugged the power supply at that moment, the subsequent problems likely wouldn’t have occurred—but of course, it’s too late now.

---

## Attempted Fixes

So, we unplugged the power and changed the battery—did that solve it?

With a mix of hope and unease, we watched the Control Hub’s blue light blinking after plugging in the power supply (this is normal behavior during Android system startup before the Robot Controller app launches).

We placed our hands on the Control Hub and found it was shockingly hot.

"Wow, it’s so hot!" I said, "This can’t be right."

ZHZ unplugged the Control Hub’s power supply and connected it to a computer using a USB Type-C cable.

Nothing happened.

I thought for a moment and found a magical Micro-USB cable to connect it to the computer.

The LED light turned on, and then…

Nothing happened.

We looked at each other.

What now?

We decided to visit the REV website for guidance.

FHY found a flowchart on the site, directing us on how to troubleshoot. Following the flowchart, we downloaded the "REV Hardware Client" app. However, without the Administrator account for the school’s computers, we couldn’t proceed.

A senior from the second year chimed in: "Let’s find the all-powerful Mr. Zhu! *^O^*"

Mr. Zhu, our club’s advisor, possesses exceptional engineering and programming skills.

Most importantly, he has the Administrator password.

We performed a "relocation ceremony"—moving everything we needed to Mr. Zhu’s office on the first floor.

Mr. Zhu launched the software and discovered:

The Control Hub was recognized as an Expansion Hub.

O_o?

Let me ask you this: How can a Control Hub be recognized as an Expansion Hub?

Where’s Android? Tell me, baby, tell me, why?

Mr. Zhu found another USB Type-C cable, connected the Control Hub to a computer, and supplied power.

The blue light turned on.

So, was it because the Type-C cable couldn’t provide power? Huh, Type-C, what’s going on with you?

I didn’t understand, but I was amazed.

Upon inspection, we saw a warning ⚠️: Unable to connect to the Robot Controller app.

Mr. Zhu began working diligently… By now, it was around 9:30 PM, and we quietly left.

---

### [March 21st After School]

Mr. Zhu said, "I updated its system and software, but it didn’t work," and handed the troublesome device back to us.

A senior had a bold idea: "Let’s connect a screen to see what’s happening inside *^O^*～"

"! (>_<)" It suddenly struck me that there’s an HDMI port on it.

Looking around, the only available screen was the Seewo display usually used as a blackboard.

We rummaged through the corners and found a cable to connect the screen.

Powered it on, and the word "REV" appeared on the screen.

After a few seconds, we saw the Robot Controller app. (If you’re curious, you can check it out yourself *^O^*)

The first line read: "network: unknown, disconnected."

The second line flashed for a moment and then displayed: "waiting for network to become active."

After a few seconds, the app crashed.

It kept repeating this.

"No wonder it’s so hot ⊙﹏⊙," a senior sighed.

Using ADB, I uninstalled the Robot Controller app and connected a keyboard.

After some tinkering, we saw in the settings that both the WiFi and Bluetooth switches were grayed out—either the driver was corrupted or the chip was damaged (WiFi and Bluetooth share the same chip).

We reported this to Mr. Zhu.

Mr. Zhu said, "Then just connect an external one. I happen to have one."

Mr. Zhu took out a WiFi module.

We attempted to use an external WiFi module!

The Control Hub rejected the attempt and emitted heat.

Mr. Zhu was defeated!

As it got late, we left the school with mixed feelings.

(PS: This method is technically feasible, but you’d need to modify the system kernel and write the driver. Unfortunately, we neither knew how to write it nor how to copy it.)

---

### [Subsequent Efforts]

- March 25: We emailed REV for support.
- March 27: After no response, we contacted the FTC China competition team.
- April 1: We received a reply from the competition team on March 28, suggesting we have Mr. Zhu disassemble the Control Hub to check for damaged components, but Mr. Zhu didn’t find anything conclusive.
- April 10: After further discussions, we identified the WiFi module and decided to replace it with a similar chip.

---

### [May 8th Club Session]

Mr. Zhu replaced the chip, and we powered it on.

Did it work?

Yes, it worked.

---

## Solution

On May 1st, while searching for the WiFi module's part number on Taobao, I found external USB adapters using the same chip. Seeing that some supported Android TV, I realized:

1. The Control Hub runs Android TV.
2. It must have drivers for this chip.

So, I ordered one and installed it on May 8th.

It worked.

---

## Lessons Learned

After reflecting on the incident, we summarized:
- Always replace the battery promptly when voltage is low!
- Don’t tell important news on April Fool’s Day!