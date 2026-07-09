This doc contains the eleven labs generated transcript from a recording of Will talking to me, doing a full review of the generated schedule, after AI generated a task graph and schedule based on the 308 scope. 

{
  "0": {
    "speaker": "speaker_0",
    "text": "I'm happy to do that. What do you want me to discuss? "
  },
  "1": {
    "speaker": "speaker_1",
    "text": "So, uh- "
  },
  "2": {
    "speaker": "speaker_0",
    "text": "All this can go down too, right? "
  },
  "3": {
    "speaker": "speaker_1",
    "text": "Yeah, that's all you. "
  },
  "4": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "5": {
    "speaker": "speaker_1",
    "text": "So I was thinking basically we should try to reconstruct an accurate PEP, and I built some tools to help us with that, so I can show you. "
  },
  "6": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "7": {
    "speaker": "speaker_1",
    "text": "Actually, you can pull it up yourself. "
  },
  "8": {
    "speaker": "speaker_0",
    "text": "What's that? "
  },
  "9": {
    "speaker": "speaker_1",
    "text": "So, pull up the site, uh, tricitiesremodeling.shop. Oops. sendurl.shop. And hopefully you can get in. Oh. "
  },
  "10": {
    "speaker": "speaker_0",
    "text": "One second. "
  },
  "11": {
    "speaker": "speaker_1",
    "text": "Oh, it's no co, no co. Um, so I built a way to actually construct these things. "
  },
  "12": {
    "speaker": "speaker_0",
    "text": "Planner? "
  },
  "13": {
    "speaker": "speaker_1",
    "text": "Pretty cool. Uh, should probably turn on lite mode. Go to your name. Yeah, account, and go lite mode. "
  },
  "14": {
    "speaker": "speaker_0",
    "text": "S- "
  },
  "15": {
    "speaker": "speaker_1",
    "text": "This was all yesterday- "
  },
  "16": {
    "speaker": "speaker_0",
    "text": "Let's see it. "
  },
  "17": {
    "speaker": "speaker_1",
    "text": "... so it's not like, uh, it's not like very finished, but we got a Gantt chart. "
  },
  "18": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "19": {
    "speaker": "speaker_1",
    "text": "And to construct these, we got a process, so basically, uh, I set it up so that it uses a scope and then optionally a breakdown. I didn't have any breakdown files but scope was enough, and then it uses, um, a JSON format of the same sheets that you're creating. "
  },
  "20": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "21": {
    "speaker": "speaker_1",
    "text": "Um, and then it also has rules which is what I want to tackle today. Basically it's just a sheet. You can see it right here, the rules, and this is basically the sheet where we can just throw a bunch of text and it's like anything and everything that the agent should know about how to do this. And I, the way I set this up is pretty much the agent is just doing the whole thing- "
  },
  "22": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "23": {
    "speaker": "speaker_1",
    "text": "... based on what it knows to do. Um- "
  },
  "24": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "25": {
    "speaker": "speaker_1",
    "text": "I have this rules file for like basically you. We can put whatever we want in here, and then I have, like, under the hood, another rules file for me to, like, put more specific instructions for how this all works. "
  },
  "26": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "27": {
    "speaker": "speaker_1",
    "text": "But we can run through an example real quick, so- "
  },
  "28": {
    "speaker": "speaker_0",
    "text": "Sure. "
  },
  "29": {
    "speaker": "speaker_1",
    "text": "... if you want to go to task graphs right there. "
  },
  "30": {
    "speaker": "speaker_0",
    "text": "Evergreen? "
  },
  "31": {
    "speaker": "speaker_1",
    "text": "And then actually you can just delete. Why don't you delete Evergreen? So hover over it and there's trash right there. "
  },
  "32": {
    "speaker": "speaker_0",
    "text": "You sure? "
  },
  "33": {
    "speaker": "speaker_1",
    "text": "Yeah, just delete it and start from scratch, and then, uh, yeah, generate a breakdown, top right, and then let's throw in the scope. If you don't have builder trend pulled up, I can, I can do this too. "
  },
  "34": {
    "speaker": "speaker_0",
    "text": "That's fine. So you want the scope and you want the breakdown for it as well? "
  },
  "35": {
    "speaker": "speaker_1",
    "text": "If you have it, yeah. "
  },
  "36": {
    "speaker": "speaker_0",
    "text": "Uh, this is one I manually tweaked, so it might throw an error or something, but we'll roll with it anyway. "
  },
  "37": {
    "speaker": "speaker_1",
    "text": "Sure. Um, as long as it's... Yeah, well, what's the- "
  },
  "38": {
    "speaker": "speaker_0",
    "text": "Here. "
  },
  "39": {
    "speaker": "speaker_1",
    "text": "... what's the negative right there? "
  },
  "40": {
    "speaker": "speaker_0",
    "text": "It's because I manually did something. I'm gonna get rid of it. "
  },
  "41": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "42": {
    "speaker": "speaker_0",
    "text": "Wills modification, 10% reduction in material, but it's okay. I'll just... I thought the materials were high. "
  },
  "43": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "44": {
    "speaker": "speaker_0",
    "text": "And I didn't want to go through it line by line, so I cheated and did that and I shouldn't have. "
  },
  "45": {
    "speaker": "speaker_1",
    "text": "Gotcha. "
  },
  "46": {
    "speaker": "speaker_0",
    "text": "Um, but it, that's fine. We'll rock and roll with this as a cost. "
  },
  "47": {
    "speaker": "speaker_1",
    "text": "All right. Just go file, top left, and get a CSV. "
  },
  "48": {
    "speaker": "speaker_0",
    "text": "Save as. "
  },
  "49": {
    "speaker": "speaker_1",
    "text": "Download CSV. "
  },
  "50": {
    "speaker": "speaker_0",
    "text": "CSV? "
  },
  "51": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "52": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "53": {
    "speaker": "speaker_1",
    "text": "And then breakdown as well, which y- the, the, uh, the text copy f- of the scope and the breakdown. "
  },
  "54": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "55": {
    "speaker": "speaker_1",
    "text": "So you can do them one at a time. "
  },
  "56": {
    "speaker": "speaker_0",
    "text": "So label this? "
  },
  "57": {
    "speaker": "speaker_1",
    "text": "Yeah, ju- whatever you want. And then copy the scope and, and the breakdown right there. "
  },
  "58": {
    "speaker": "speaker_0",
    "text": "Uh, it's PEP I guess, right? "
  },
  "59": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "60": {
    "speaker": "speaker_0",
    "text": "Do you want the cost in here too like this? "
  },
  "61": {
    "speaker": "speaker_1",
    "text": "Um, yeah, that's, that's good. "
  },
  "62": {
    "speaker": "speaker_0",
    "text": "Okay. Breakdown narrative, optional. How do I put the file in here? "
  },
  "63": {
    "speaker": "speaker_1",
    "text": "Uh, what, what's the format of your breakdowns? "
  },
  "64": {
    "speaker": "speaker_0",
    "text": "Well, right now they're CSV. That's what we just downloaded. "
  },
  "65": {
    "speaker": "speaker_1",
    "text": "Oh, this is- "
  },
  "66": {
    "speaker": "speaker_0",
    "text": "This is the breakdown. "
  },
  "67": {
    "speaker": "speaker_1",
    "text": "Oh, okay. I thought there was like a third. Okay, perfect. Okay, so go back, and then click upload to CD. It's gonna convert it, so- "
  },
  "68": {
    "speaker": "speaker_0",
    "text": "This right there? "
  },
  "69": {
    "speaker": "speaker_1",
    "text": "Right there. Click that. It's gonna have you find that file. Should upload it. It's gonna take a sec. It's gonna put it in JSON, which is just standard format to put it in, and then it'll run for another like two minutes once you click generate, and it's gonna make basically... Yep, there you go. You can click generate. It's gonna make a list of phases, components, and tasks. Each task has dependencies and, uh, duration, trade.... and that's all they really need is, like just a long list of those things, and then I have an engine that takes a list like that and makes an efficient schedule from it. So you can actually visualize what that list looks like on a Gantt chart. "
  },
  "70": {
    "speaker": "speaker_0",
    "text": "Awesome. "
  },
  "71": {
    "speaker": "speaker_1",
    "text": "And so I was thinking we should look at that and see how accurate it would be against- "
  },
  "72": {
    "speaker": "speaker_0",
    "text": "What I would make? "
  },
  "73": {
    "speaker": "speaker_1",
    "text": "Yeah. And you can't blame me because it's all AI. "
  },
  "74": {
    "speaker": "speaker_0",
    "text": "(laughs) "
  },
  "75": {
    "speaker": "speaker_1",
    "text": "(laughs) "
  },
  "76": {
    "speaker": "speaker_0",
    "text": "Um, Jeremy, do you care to close the door, just so I'm not, we're not being too loud for everybody? (door closes) Thank you. Okay, so the only output right now is the schedule? "
  },
  "77": {
    "speaker": "speaker_1",
    "text": "Um, pretty much. "
  },
  "78": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "79": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "80": {
    "speaker": "speaker_0",
    "text": "This is the Gantt chart? "
  },
  "81": {
    "speaker": "speaker_1",
    "text": "Should be enough for us to like get a good idea of how, like how close we are, um, and really, like I was trying really hard last night to, to like ask, like, \"How do we make this more like structured in the meantime?\" And it was basically saying just like literally just spitball all the rules right into that text document, and that's like the best place to start. "
  },
  "82": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "83": {
    "speaker": "speaker_1",
    "text": "Um, and it's been doing a great job. "
  },
  "84": {
    "speaker": "speaker_0",
    "text": "Um, (knocks on table) okay. I'm trying to think. Do you want me to try to make a PEP, like what the output will look like live? For you, is that what you wanted to record, or what did you want to record specifically? "
  },
  "85": {
    "speaker": "speaker_1",
    "text": "Basically, I want to, um, I wanna kinda get like your, like in-detail, uh, review of what it's putting out, see how far off it actually is. "
  },
  "86": {
    "speaker": "speaker_0",
    "text": "Sure. "
  },
  "87": {
    "speaker": "speaker_1",
    "text": "And then, um, start to think about what kind of rules you actually would want to have in place for it to kinda have a general understanding. (notification chime) Here we go. So like- "
  },
  "88": {
    "speaker": "speaker_0",
    "text": "(knocks on table) "
  },
  "89": {
    "speaker": "speaker_1",
    "text": "Yeah. I'll, I'll try not to like talk, basically to have a conversation about rules. "
  },
  "90": {
    "speaker": "speaker_0",
    "text": "Yeah. "
  },
  "91": {
    "speaker": "speaker_1",
    "text": "And that's why I'm recording, so that we can, uh, not even have to write it. We can just talk and get your expertise. "
  },
  "92": {
    "speaker": "speaker_0",
    "text": "Awesome. "
  },
  "93": {
    "speaker": "speaker_1",
    "text": "So this is the list. All the blue is phases, like pre-construction, site work, excavation. "
  },
  "94": {
    "speaker": "speaker_0",
    "text": "Excavation. Nice. "
  },
  "95": {
    "speaker": "speaker_1",
    "text": "And then each one, all the uppercase are the components, and the lowercase are the tasks right there. "
  },
  "96": {
    "speaker": "speaker_0",
    "text": "Okay, so phase, component, task? "
  },
  "97": {
    "speaker": "speaker_1",
    "text": "Yup. "
  },
  "98": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "99": {
    "speaker": "speaker_1",
    "text": "And then each one has a trade, and a duration, and dependencies. Um, and I set it up so that we can edit these, but before we do that, we should see what it actually looks like. So you can go to the top right and click the start, like to the left of that. "
  },
  "100": {
    "speaker": "speaker_0",
    "text": "Oh, this? "
  },
  "101": {
    "speaker": "speaker_1",
    "text": "So we can pick a start date. "
  },
  "102": {
    "speaker": "speaker_0",
    "text": "Sure. "
  },
  "103": {
    "speaker": "speaker_1",
    "text": "Go to like June. "
  },
  "104": {
    "speaker": "speaker_0",
    "text": "We'll say Monday. We'll say Monday, like this coming Monday. Could you- "
  },
  "105": {
    "speaker": "speaker_1",
    "text": "Sure, that should be fine, I think. "
  },
  "106": {
    "speaker": "speaker_0",
    "text": "Do you want me to put it out further? "
  },
  "107": {
    "speaker": "speaker_1",
    "text": "Go further out, I think. "
  },
  "108": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "109": {
    "speaker": "speaker_1",
    "text": "I haven't tested if it was- "
  },
  "110": {
    "speaker": "speaker_0",
    "text": "29? "
  },
  "111": {
    "speaker": "speaker_1",
    "text": "Yeah, perfect. "
  },
  "112": {
    "speaker": "speaker_0",
    "text": "And then run it? "
  },
  "113": {
    "speaker": "speaker_1",
    "text": "Yup. And that was just code, so, uh, it's not, that's not AI at all. It's just like an engine that uses whatever that was and makes a schedule with it. "
  },
  "114": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "115": {
    "speaker": "speaker_1",
    "text": "So this is the same list, uh, but turned into, like basically a timeline based on what was depending on what. That's how it knows how to lay out the structure. "
  },
  "116": {
    "speaker": "speaker_0",
    "text": "Dude, awesome. Okay, so this is this phase, obviously. "
  },
  "117": {
    "speaker": "speaker_1",
    "text": "Yup. "
  },
  "118": {
    "speaker": "speaker_0",
    "text": "And this is the specific task. "
  },
  "119": {
    "speaker": "speaker_1",
    "text": "Yup. "
  },
  "120": {
    "speaker": "speaker_0",
    "text": "So this is this task, this task, this task, and then this is dump and removal. "
  },
  "121": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "122": {
    "speaker": "speaker_0",
    "text": "Okay. Utilities, you're like, okay, this can run concurrently with interior demo. "
  },
  "123": {
    "speaker": "speaker_1",
    "text": "Yeah, this is pretty much where you have to just like review everything and be- 'cause I, I just don't know what's correct or not. "
  },
  "124": {
    "speaker": "speaker_0",
    "text": "No, you're good. "
  },
  "125": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "126": {
    "speaker": "speaker_0",
    "text": "Okay. So what I'll do is I'll pull, I'm gonna pull the scope to my other screen- "
  },
  "127": {
    "speaker": "speaker_1",
    "text": "Perfect. "
  },
  "128": {
    "speaker": "speaker_0",
    "text": "... take a look at it, and then I'll bring it over as it's relevant. Um, actually, if you guys don't care, I can... Yeah, that, I think that would be too much. Okay. So demo. Do you want me to start it when the job starts or do you want me to go over here as well? Does it matter? "
  },
  "129": {
    "speaker": "speaker_1",
    "text": "Yeah, yeah. I mean, uh, as well as you can, start from the, the beginning. "
  },
  "130": {
    "speaker": "speaker_0",
    "text": "Okay. Um, obtain building permit? That can, that can just be like a day. It doesn't need to be however long this says that it is. "
  },
  "131": {
    "speaker": "speaker_1",
    "text": "Sure. Although, it probably takes a while to get back, yeah? "
  },
  "132": {
    "speaker": "speaker_0",
    "text": "No. "
  },
  "133": {
    "speaker": "speaker_1",
    "text": "No? "
  },
  "134": {
    "speaker": "speaker_0",
    "text": "I, a lot of times I can get them, like I walk in there with documentation, I walk out with a permit. "
  },
  "135": {
    "speaker": "speaker_1",
    "text": "Oh, cool. So, um, so we probably- "
  },
  "136": {
    "speaker": "speaker_0",
    "text": "Most of the time, not all the time, but most, probably 90% of the time, unless a fluke happens. "
  },
  "137": {
    "speaker": "speaker_1",
    "text": "This is like nearly five weeks ahead of job start. Is that over the top? "
  },
  "138": {
    "speaker": "speaker_0",
    "text": "Yeah, I mean, no. It doesn't, doesn't have to be. "
  },
  "139": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "140": {
    "speaker": "speaker_0",
    "text": "You know? Um... "
  },
  "141": {
    "speaker": "speaker_1",
    "text": "Like, what about these other things, like there's fo- three other things? Like- "
  },
  "142": {
    "speaker": "speaker_0",
    "text": "Do you want me to take notes anywhere? "
  },
  "143": {
    "speaker": "speaker_1",
    "text": "I guess, I guess we could do that. "
  },
  "144": {
    "speaker": "speaker_0",
    "text": "I think that's what this is for. Okay, okay. "
  },
  "145": {
    "speaker": "speaker_1",
    "text": "(laughs) Uh- "
  },
  "146": {
    "speaker": "speaker_0",
    "text": "I just, I'm not used to not taking notes, so. "
  },
  "147": {
    "speaker": "speaker_1",
    "text": "Sure, sure. "
  },
  "148": {
    "speaker": "speaker_0",
    "text": "Uh, obtain building permit, yeah, that can just be a day and a minimum of three weeks prior to the start date. "
  },
  "149": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "150": {
    "speaker": "speaker_0",
    "text": "That would be fine. The TDEC thing, that definitely needs to be early. "
  },
  "151": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "152": {
    "speaker": "speaker_0",
    "text": "Um, what is this, four weeks prior? "
  },
  "153": {
    "speaker": "speaker_1",
    "text": "Four and a half, yeah. "
  },
  "154": {
    "speaker": "speaker_0",
    "text": "Okay. So that is definitely what we need to do there. So as far as the TDEC septic inspection and coordination, so w- the initial thing we do is we call TDEC to get them, like there's more steps to this.... T deck, we have to call them to sort out, ge- scheduling, paying $500 per permit, and then scheduling them to come out and do their, like, little test. And then we get, uh, a report back from a soil scientist. "
  },
  "155": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "156": {
    "speaker": "speaker_0",
    "text": "So there's, like, three or four steps there, right? "
  },
  "157": {
    "speaker": "speaker_1",
    "text": "Yep. And how many weeks before job start do you need that, that- "
  },
  "158": {
    "speaker": "speaker_0",
    "text": "Like, five, six weeks. Like, what, what, what you have here is great. "
  },
  "159": {
    "speaker": "speaker_1",
    "text": "So you need, you need them to come, like, four or five weeks? "
  },
  "160": {
    "speaker": "speaker_0",
    "text": "Yes. Because it could take them a while to build out their, their plan. "
  },
  "161": {
    "speaker": "speaker_1",
    "text": "So how far ahead do you need to actually, like, set that up? "
  },
  "162": {
    "speaker": "speaker_0",
    "text": "The ini- the initial contact says six weeks. "
  },
  "163": {
    "speaker": "speaker_1",
    "text": "Six weeks? All right. "
  },
  "164": {
    "speaker": "speaker_0",
    "text": "Um- "
  },
  "165": {
    "speaker": "speaker_1",
    "text": "Is that a standard for almost all jobs? "
  },
  "166": {
    "speaker": "speaker_0",
    "text": "T- T deck is the most non-typical thing. Like, they can take a long time. They can take ... They can go pretty quick. "
  },
  "167": {
    "speaker": "speaker_1",
    "text": "So you need a lot of time? "
  },
  "168": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "169": {
    "speaker": "speaker_1",
    "text": "You can't really predict? "
  },
  "170": {
    "speaker": "speaker_0",
    "text": "Yes. Yes. So five, six weeks before the job starts, we would w- need to do the initial for this, and then hopefully get the report back in a week or two, and then go from there. "
  },
  "171": {
    "speaker": "speaker_1",
    "text": "Good to know. "
  },
  "172": {
    "speaker": "speaker_0",
    "text": "Does that make sense? "
  },
  "173": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "174": {
    "speaker": "speaker_0",
    "text": "Um, finalize selections. Um, that is great to have it done five weeks ahead, but it can be a couple weeks ahead, right? "
  },
  "175": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "176": {
    "speaker": "speaker_0",
    "text": "From anywhere between five and three weeks before we start. "
  },
  "177": {
    "speaker": "speaker_1",
    "text": "So it has to be done three weeks ... So it sh- there should be, like, a checkpoint three weeks before? "
  },
  "178": {
    "speaker": "speaker_0",
    "text": "Before we start, yes. Yeah. "
  },
  "179": {
    "speaker": "speaker_1",
    "text": "Yeah. So this is set up to have checkpoints. There shou- it's just not using a lot of them. If you scroll to the ... you don't have to, but the ... "
  },
  "180": {
    "speaker": "speaker_0",
    "text": "No. Th- this- "
  },
  "181": {
    "speaker": "speaker_1",
    "text": "... the project end, it's, uh, has a, like, job end checkpoint, and there might be- "
  },
  "182": {
    "speaker": "speaker_0",
    "text": "All the way down? "
  },
  "183": {
    "speaker": "speaker_1",
    "text": "Yeah, yeah, yeah. All the way down here. That's ... So these, like, diamonds are, are checkpoints, and there's, there might be a couple of them sprinkled in. "
  },
  "184": {
    "speaker": "speaker_0",
    "text": "Oh, cool. "
  },
  "185": {
    "speaker": "speaker_1",
    "text": "But it's mostly just putting these, like, items in. "
  },
  "186": {
    "speaker": "speaker_0",
    "text": "Okay. "
  },
  "187": {
    "speaker": "speaker_1",
    "text": "Uh, but I think that would be the goal, is to have more of those in place. "
  },
  "188": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "189": {
    "speaker": "speaker_1",
    "text": "To know where checkpoints need to be. "
  },
  "190": {
    "speaker": "speaker_0",
    "text": "For sure. "
  },
  "191": {
    "speaker": "speaker_1",
    "text": "Awesome. "
  },
  "192": {
    "speaker": "speaker_0",
    "text": "Um, but yeah, so finalizing the selections three weeks prior to the job start, that's, that's like the latest I would want it. "
  },
  "193": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "194": {
    "speaker": "speaker_0",
    "text": "Um, we can go a little bit later, but, like, for str- you know, streamline purposes, that's what I would do. "
  },
  "195": {
    "speaker": "speaker_1",
    "text": "Yeah. I'm glad it, it got the ordering of the LVL, 'cause you said yesterday that needs to be, like, f- far ahead of time, yeah? "
  },
  "196": {
    "speaker": "speaker_0",
    "text": "No, the LVL doesn't ... Trusses do. "
  },
  "197": {
    "speaker": "speaker_1",
    "text": "Hmm. "
  },
  "198": {
    "speaker": "speaker_0",
    "text": "LVLs, like, a week before we start is fine- "
  },
  "199": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "200": {
    "speaker": "speaker_0",
    "text": "... for LVL beams. Um, they're usually readily available, unless we're getting pressure treated ones or something like that. "
  },
  "201": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "202": {
    "speaker": "speaker_0",
    "text": "So, actually, okay, I'll take that back. If you wanna set a rule for it, set it three weeks prior. That way the PM does it three weeks prior just in case it's a pressure treated or whatever the, they need. Something custom that they need to order. Order windows and doors. Yep, doing that weeks ahead of time is fine. Mini-split and tankless hot water heater. We don't have to do that until, like ... I need to press purchase when the building's dried in or just about dried in, because it's all mechanical stuff. "
  },
  "203": {
    "speaker": "speaker_1",
    "text": "So when would that be? "
  },
  "204": {
    "speaker": "speaker_0",
    "text": "When it's dried in, so that w- "
  },
  "205": {
    "speaker": "speaker_1",
    "text": "When it's dried in? "
  },
  "206": {
    "speaker": "speaker_0",
    "text": "W- it's dried in after all of my roofing si- this. Like, roof and exterior and dry-in. "
  },
  "207": {
    "speaker": "speaker_1",
    "text": "Okay. So that's, like, during the job. "
  },
  "208": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "209": {
    "speaker": "speaker_1",
    "text": "Okay. So that's add a place. "
  },
  "210": {
    "speaker": "speaker_0",
    "text": "Yep. For the mini-split and the tankless w- hot water heater. We need to have the selections done, but that's part of, uh, the, uh ... "
  },
  "211": {
    "speaker": "speaker_1",
    "text": "Finalize? "
  },
  "212": {
    "speaker": "speaker_0",
    "text": "Yeah. "
  },
  "213": {
    "speaker": "speaker_1",
    "text": "Yeah. Finalize? "
  },
  "214": {
    "speaker": "speaker_0",
    "text": "Let's finalize selections and stuff. Um, order vanity mirrors, same thing. I need that at dry-in, when dry-in's done or just about done. "
  },
  "215": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "216": {
    "speaker": "speaker_0",
    "text": "Um, same thing with tile and waterproofing, same thing with LVT, all this stuff. This is all interior finish stuff. "
  },
  "217": {
    "speaker": "speaker_1",
    "text": "Right. Um, although this is bas- this is a different scenar- scenario though, because this is a project where you're actually doing a roof. If you weren't, then, uh, how would it be different? "
  },
  "218": {
    "speaker": "speaker_0",
    "text": "I mean, if we're doing just a bathroom, I need it right away, 'cause it's ... we're just jumping right into finish work. "
  },
  "219": {
    "speaker": "speaker_1",
    "text": "But if you need them right away, when do you have to order them? "
  },
  "220": {
    "speaker": "speaker_0",
    "text": "We need to order them, like, two or three weeks before the project starts. "
  },
  "221": {
    "speaker": "speaker_1",
    "text": "So if we weren't doing a roof, this would be right ... "
  },
  "222": {
    "speaker": "speaker_0",
    "text": "... Correct. "
  },
  "223": {
    "speaker": "speaker_1",
    "text": "... here? Okay. "
  },
  "224": {
    "speaker": "speaker_0",
    "text": "If we were doing a remodel. It depends on the job, right? "
  },
  "225": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "226": {
    "speaker": "speaker_0",
    "text": "But, like, because this is an addition, and this ... It's because this stuff, the ord- like, when I need this stuff is m- weeks down the road. "
  },
  "227": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "228": {
    "speaker": "speaker_0",
    "text": "That's why. If it was ... Like, these, ordering of this stuff can be tied to when we do those actions. "
  },
  "229": {
    "speaker": "speaker_1",
    "text": "Right. "
  },
  "230": {
    "speaker": "speaker_0",
    "text": "Right? "
  },
  "231": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "232": {
    "speaker": "speaker_0",
    "text": "And I want 'em, like, a week or two prior to when we need them. "
  },
  "233": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "234": {
    "speaker": "speaker_0",
    "text": "Right? So if we're doing a remodel job that's a bathroom, there isn't any of this. It's just right to the front. "
  },
  "235": {
    "speaker": "speaker_1",
    "text": "Yeah. I think that would be- "
  },
  "236": {
    "speaker": "speaker_0",
    "text": "Does that make sense? "
  },
  "237": {
    "speaker": "speaker_1",
    "text": "... one of the most important things to start filling the rules out with, is actually attaching things to other job phases. "
  },
  "238": {
    "speaker": "speaker_0",
    "text": "To phases of the job. "
  },
  "239": {
    "speaker": "speaker_1",
    "text": "Exactly. "
  },
  "240": {
    "speaker": "speaker_0",
    "text": "Yeah. "
  },
  "241": {
    "speaker": "speaker_1",
    "text": "So maybe it being, like, if you're ever doing this, the rule is, if we're doing a roof, then you do it like, T-minus three weeks from when the roof dry-in is done, but otherwise then it's minus three weeks from job start. "
  },
  "242": {
    "speaker": "speaker_0",
    "text": "Correct. "
  },
  "243": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "244": {
    "speaker": "speaker_0",
    "text": "Yeah. It's ... So you could tie it that I want the interior finish materials there one week before we start the interior finish work. "
  },
  "245": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "246": {
    "speaker": "speaker_0",
    "text": "Regardless of the project, right? So that way it's not tied to if we're doing a roof or if we're not doing a roof, or anything like that. It's just tied to the actual work that these materials need to be installed at. Does that make sense? "
  },
  "247": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "248": {
    "speaker": "speaker_0",
    "text": "Um, cool. So, that's all that stuff. Uh, the other thing that I wanna say that I don't see on here, and it's because it's not in the scope: I want the project managers, as part of their general procedure, to make a material ordering schedule, which goes in here. But that way, they say, \"Hey, this day, this day, this day.\" I mean, I guess that's kind of what this is. "
  },
  "249": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "250": {
    "speaker": "speaker_0",
    "text": "So, nevermind.Site work and demo. "
  },
  "251": {
    "speaker": "speaker_1",
    "text": "Do they actually order the materials or do you have someone who does- who manages all that? "
  },
  "252": {
    "speaker": "speaker_0",
    "text": "PM does it. "
  },
  "253": {
    "speaker": "speaker_1",
    "text": "He does it. Okay. "
  },
  "254": {
    "speaker": "speaker_0",
    "text": "PM orders his own materials. I am open to getting somebody that just does ordering for the PMs. "
  },
  "255": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "256": {
    "speaker": "speaker_0",
    "text": "But we'd probably need three or four, like, p- project managers for that to be worth it. "
  },
  "257": {
    "speaker": "speaker_1",
    "text": "Yeah, man. "
  },
  "258": {
    "speaker": "speaker_0",
    "text": "(clears throat) Um, as far as the site demo, cut and saw way, remove concrete, railroad ties and obstructions into your demo. So one thing that I don't see on here is we have to coordinate equipment for the site demo, right? Like we're gonna need a concrete saw, probably a skid steer, a mini ex to dig the footers, um, and things like that. So we have to coordinate, like, that equipment. Th- that- that needs to be on site. Um, it could be on site the day before the work starts. "
  },
  "259": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "260": {
    "speaker": "speaker_0",
    "text": "And- and it probably should, because that equipment costs money. You know, whether it's my equipment or I rented it. "
  },
  "261": {
    "speaker": "speaker_1",
    "text": "So checkpoint, make sure everything is on- on site day before demo phase starts. "
  },
  "262": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "263": {
    "speaker": "speaker_1",
    "text": "And arrange how far in advance? "
  },
  "264": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "265": {
    "speaker": "speaker_1",
    "text": "Like, how far? Like, one week? Two weeks? How- how far ahead do you need to have, like- "
  },
  "266": {
    "speaker": "speaker_0",
    "text": "Do we need to have them coordinating it? "
  },
  "267": {
    "speaker": "speaker_1",
    "text": "... to have the guarantee that it will be ready? "
  },
  "268": {
    "speaker": "speaker_0",
    "text": "Uh, two weeks prior, we'll guarantee it. One week prior, you could probably still accomplish it. "
  },
  "269": {
    "speaker": "speaker_1",
    "text": "Yeah, two weeks is good. "
  },
  "270": {
    "speaker": "speaker_0",
    "text": "Okay. Um... And then the other thing, like, uh, you know, in the site work, debris removal and dump runs, we don't have anywhere where it says, \"Deliver dump- dumpster on site.\" "
  },
  "271": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "272": {
    "speaker": "speaker_0",
    "text": "Right? So that needs to be done also the day before. "
  },
  "273": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "274": {
    "speaker": "speaker_0",
    "text": "Um, relocate key pump and electrical disconnect. This stuff should be done before the site work and demo. This should be done, like, relocating the heat pumps and electrical disconnects. We don't want... Th- that stuff has to be moved before demo crew can do the demo stuff. So this needs to come before this demolition site work phase. "
  },
  "275": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "276": {
    "speaker": "speaker_0",
    "text": "Like this should... You can call this kicking off the project, you can call it technical work before the main project starts. Whatever you want to call it is fine. "
  },
  "277": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "278": {
    "speaker": "speaker_0",
    "text": "But that needs to be done pro- at- at a minimum of three days prior to us beginning the demo. "
  },
  "279": {
    "speaker": "speaker_1",
    "text": "Gotcha. So it's out of place. Where- where does it show up right now? "
  },
  "280": {
    "speaker": "speaker_0",
    "text": "Right now? "
  },
  "281": {
    "speaker": "speaker_1",
    "text": "Y- you can just click it, it scrolls to it. "
  },
  "282": {
    "speaker": "speaker_0",
    "text": "Oh, okay. Cool. So it happens right after the demo? "
  },
  "283": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "284": {
    "speaker": "speaker_0",
    "text": "Or, like, as the demo phase finishes. "
  },
  "285": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "286": {
    "speaker": "speaker_0",
    "text": "But yeah. "
  },
  "287": {
    "speaker": "speaker_1",
    "text": "Out of place. "
  },
  "288": {
    "speaker": "speaker_0",
    "text": "Yeah. This one's out of place. This one has to be done before we ever start the demolition, the main demo. Um, it looks like to me something is missing as well. So this is the site work and demo. Oh, okay. Never mind. No, we're good. Excavation and foundation. Excavation, footing and slab area. This has three days. "
  },
  "289": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "290": {
    "speaker": "speaker_0",
    "text": "Yeah, that's probably fine. It might take two days instead of three. Um, again, this is my opinion. "
  },
  "291": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "292": {
    "speaker": "speaker_0",
    "text": "Whatever I put on the job breakdown is prob- is definitely going to be more accurate. Form rebar perimeter footings. This should probably take like two or three days instead of four days. "
  },
  "293": {
    "speaker": "speaker_1",
    "text": "It... No, it has three. So, um, those are... These are weekend. "
  },
  "294": {
    "speaker": "speaker_0",
    "text": "Oh. "
  },
  "295": {
    "speaker": "speaker_1",
    "text": "So it's a little confusing. I put all holidays in dark gray. "
  },
  "296": {
    "speaker": "speaker_0",
    "text": "Mm-hmm. "
  },
  "297": {
    "speaker": "speaker_1",
    "text": "And then all the light grays are the weekends. So- "
  },
  "298": {
    "speaker": "speaker_0",
    "text": "Gotcha. "
  },
  "299": {
    "speaker": "speaker_1",
    "text": "... it's technically three work days. Three- "
  },
  "300": {
    "speaker": "speaker_0",
    "text": "Okay. Well, then with that being said, FYI, Friday the 3rd is off. Like, that's a federal holiday. "
  },
  "301": {
    "speaker": "speaker_1",
    "text": "Right. "
  },
  "302": {
    "speaker": "speaker_0",
    "text": "This year. Just FYI. "
  },
  "303": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "304": {
    "speaker": "speaker_0",
    "text": "So you probably just want to update this for federal holidays. "
  },
  "305": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. Yeah, I can- "
  },
  "306": {
    "speaker": "speaker_0",
    "text": "So it's just the schedule. "
  },
  "307": {
    "speaker": "speaker_1",
    "text": "... I can- I can put all the holidays. I have, like, a sheet for it. Yeah. "
  },
  "308": {
    "speaker": "speaker_0",
    "text": "Cool. Um, footing inspection. Yep, that's fine. Pour the footings. "
  },
  "309": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "310": {
    "speaker": "speaker_0",
    "text": "So there's a big... Okay, so for this, we probably have the gravel base vapor bar- like this phase comes right after the footings. And then we're doing both then the inspection, and then we're doing both pours at once. Does that make sense? So you pour the footings and the slab at the same time. "
  },
  "311": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "312": {
    "speaker": "speaker_0",
    "text": "It's called a monolithic pour. "
  },
  "313": {
    "speaker": "speaker_1",
    "text": "Yep. So they can all be same- same day as inspections, same day as imports, same day... "
  },
  "314": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "315": {
    "speaker": "speaker_1",
    "text": "Yeah. I don't know why it has a gap in here. "
  },
  "316": {
    "speaker": "speaker_0",
    "text": "Traditionally, like w- if you don't do monolithic pours, this is what you have to do. "
  },
  "317": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "318": {
    "speaker": "speaker_0",
    "text": "And there needs to be a- a secondary inspection for the slab. Does that make sense? "
  },
  "319": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "320": {
    "speaker": "speaker_0",
    "text": "So it'd be form this, and then this immediately after with the gravel base and vapor barrier, and then the inspection. "
  },
  "321": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "322": {
    "speaker": "speaker_0",
    "text": "And then the pour of the footings and the slab at the same time. And also that is all going to be in one day. This is a one-day pour- "
  },
  "323": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "324": {
    "speaker": "speaker_0",
    "text": "... for everything. (coughs) "
  },
  "325": {
    "speaker": "speaker_1",
    "text": "So this... So you always do it that way? "
  },
  "326": {
    "speaker": "speaker_0",
    "text": "95% of the time. It's going to be very rare that I don't do monolithic. "
  },
  "327": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "328": {
    "speaker": "speaker_0",
    "text": "Um, does that work? "
  },
  "329": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "330": {
    "speaker": "speaker_0",
    "text": "Makes sense? Okay. Framing and structural. So it looks like between the pour and the slab and the temporary shoring, there's a lag day. "
  },
  "331": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "332": {
    "speaker": "speaker_0",
    "text": "There doesn't have to be. Just FYI. There would be if we just started framing, but this is like inside the home work. "
  },
  "333": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "334": {
    "speaker": "speaker_0",
    "text": "Um... "
  },
  "335": {
    "speaker": "speaker_1",
    "text": "What's your dry time on the...... slab probably along a week at least, right, before you- "
  },
  "336": {
    "speaker": "speaker_0",
    "text": "You can wait just- "
  },
  "337": {
    "speaker": "speaker_1",
    "text": "... build on it. "
  },
  "338": {
    "speaker": "speaker_0",
    "text": "... two days is fine. "
  },
  "339": {
    "speaker": "speaker_1",
    "text": "Right. "
  },
  "340": {
    "speaker": "speaker_0",
    "text": "Um, some people build on it the next day. A minimum of two days, a week, is good. So there's- "
  },
  "341": {
    "speaker": "speaker_1",
    "text": "I see. "
  },
  "342": {
    "speaker": "speaker_0",
    "text": "... flexibility there. "
  },
  "343": {
    "speaker": "speaker_1",
    "text": "I see. Okay. "
  },
  "344": {
    "speaker": "speaker_0",
    "text": "Um, temporary shoring for that, that can happen immediately. There's not, like, a need for a delay there. Um, basement walls, yeah, so this, framing the basement walls is gonna be, like, you have your lag days after the pour of the slab. So it's two to seven days. It's really up to the project manager, and then he can start framing the walls. Okay. This is an independent. The temporary shoring for the LVL is independent, and it's also just gonna take one day maybe. "
  },
  "345": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "346": {
    "speaker": "speaker_0",
    "text": "Frame floor system and subfloor, yeah, this is, has to be after framing the walls. "
  },
  "347": {
    "speaker": "speaker_1",
    "text": "So, um, let's see. "
  },
  "348": {
    "speaker": "speaker_0",
    "text": "Which it is right now. It's in the right place. "
  },
  "349": {
    "speaker": "speaker_1",
    "text": "Right, but just click on that real quick and see. It depends on framing basement walls. Cool. Okay. "
  },
  "350": {
    "speaker": "speaker_0",
    "text": "It is not dependent on this. "
  },
  "351": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "352": {
    "speaker": "speaker_0",
    "text": "It's just dependent on the framing of the basement walls, not the framing, shoring of the LVL. "
  },
  "353": {
    "speaker": "speaker_1",
    "text": "Gotcha. So, yeah, it's probably, I'm assuming, what it has right now is there's four different types of dependencies. FS means finish start, like finish then start- "
  },
  "354": {
    "speaker": "speaker_0",
    "text": "Mm-hmm. "
  },
  "355": {
    "speaker": "speaker_1",
    "text": "But there's also a lag input, so you can do minus, so it's probably a minus one day lag on the finish of the shoring, but- "
  },
  "356": {
    "speaker": "speaker_0",
    "text": "Sure. "
  },
  "357": {
    "speaker": "speaker_1",
    "text": "... that can sh- be deleted. "
  },
  "358": {
    "speaker": "speaker_0",
    "text": "Yeah. "
  },
  "359": {
    "speaker": "speaker_1",
    "text": "But, um, so you're- "
  },
  "360": {
    "speaker": "speaker_0",
    "text": "Framing oper- "
  },
  "361": {
    "speaker": "speaker_1",
    "text": "... saying that can happen at the same time? Is... Like, all three can happen at the same time? "
  },
  "362": {
    "speaker": "speaker_0",
    "text": "No. The walls have to go up first. The floor has to go up second. "
  },
  "363": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "364": {
    "speaker": "speaker_0",
    "text": "The temporary shoring for the LVL can happen anytime. It's not- "
  },
  "365": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "366": {
    "speaker": "speaker_0",
    "text": "... dependent on anything. "
  },
  "367": {
    "speaker": "speaker_1",
    "text": "Right, right, right. "
  },
  "368": {
    "speaker": "speaker_0",
    "text": "Oh, right. "
  },
  "369": {
    "speaker": "speaker_1",
    "text": "Specific to a basement, right? Or to a slab? "
  },
  "370": {
    "speaker": "speaker_0",
    "text": "So this is the second story where we're taking out that wall. "
  },
  "371": {
    "speaker": "speaker_1",
    "text": "Oh, okay. "
  },
  "372": {
    "speaker": "speaker_0",
    "text": "Right? So I'll pull up the plans just so you guys have an understanding. Uh, since that's, no, not that. So on the second story, where we're taking out this large wall, the- that's where the LVL is gonna go. On the basement, they still have that exterior wall. We just have a door. "
  },
  "373": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "374": {
    "speaker": "speaker_0",
    "text": "So you don't need an LVL beam. You can just have a stick frame header. "
  },
  "375": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "376": {
    "speaker": "speaker_0",
    "text": "Right? But in order to open this up, like, op- like, temporary shoring for this is not dependent on anything. "
  },
  "377": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "378": {
    "speaker": "speaker_0",
    "text": "Like, it does... You can have the entire building built. Does not, this does not matter. "
  },
  "379": {
    "speaker": "speaker_1",
    "text": "Hm. "
  },
  "380": {
    "speaker": "speaker_0",
    "text": "It only matters when you wanna poke through the wall. Does that make sense? "
  },
  "381": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "382": {
    "speaker": "speaker_0",
    "text": "Um, so yeah, the temporary shoring is an independent item here. "
  },
  "383": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "384": {
    "speaker": "speaker_0",
    "text": "Uh, frame upper exterior and interior walls. Yep, that's fine. Frame elevator shaft is fine. Frame shed and roof, dependent on this. What's this dependency? SS_Lag_01. "
  },
  "385": {
    "speaker": "speaker_1",
    "text": "Um, yeah, that means it's dependent on the upper walls, uh, starting as well. It's dependent on- "
  },
  "386": {
    "speaker": "speaker_0",
    "text": "Okay. FY- "
  },
  "387": {
    "speaker": "speaker_1",
    "text": "... well- "
  },
  "388": {
    "speaker": "speaker_0",
    "text": "FYI, it doesn't have to be, and that's because of where it is. Like, because the elevator is over here- "
  },
  "389": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "390": {
    "speaker": "speaker_0",
    "text": "... and it's not even close to the addition over here- "
  },
  "391": {
    "speaker": "speaker_1",
    "text": "Gotcha. "
  },
  "392": {
    "speaker": "speaker_0",
    "text": "... it's a retrofit item, and- "
  },
  "393": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "394": {
    "speaker": "speaker_0",
    "text": "... the retrofit item is not dependent on this. "
  },
  "395": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "396": {
    "speaker": "speaker_0",
    "text": "And tha- that's also why the LVL is up, because it's a retrofit, you know. Um, shedroof system, that's fine. What is this? Roof and wall sheathing, that's fine. Okay. So then the next is this, framing inspection? "
  },
  "397": {
    "speaker": "speaker_1",
    "text": "Yup. "
  },
  "398": {
    "speaker": "speaker_0",
    "text": "So the fra- it's stupid as hell, and I don't know why they do this here. You cannot get a framing inspection until after your MEPs have passed rough-in. "
  },
  "399": {
    "speaker": "speaker_1",
    "text": "Hm. "
  },
  "400": {
    "speaker": "speaker_0",
    "text": "Stupid. But the reason they do it is if you're, if you go and after you dry the building in, right, and it's framed, you get your framing inspection, and then your plumber, because he wants to be a jackwad drills a whole- "
  },
  "401": {
    "speaker": "speaker_1",
    "text": "Constrains. "
  },
  "402": {
    "speaker": "speaker_0",
    "text": "... hole in the beam. "
  },
  "403": {
    "speaker": "speaker_1",
    "text": "Oh, yeah. "
  },
  "404": {
    "speaker": "speaker_0",
    "text": "And then you do your plumbing inspection, you passed framing, and you passed plumbing because Mr. Jackwad drilled through a beam. So you can't get a framing inspection until after MEP inspections, FYI. Okay? Does that make sense? "
  },
  "405": {
    "speaker": "speaker_1",
    "text": "Yeah. (laughs) "
  },
  "406": {
    "speaker": "speaker_0",
    "text": "(laughs) So yeah. The framing inspec- "
  },
  "407": {
    "speaker": "speaker_1",
    "text": "Why does that happen so often? "
  },
  "408": {
    "speaker": "speaker_0",
    "text": "Huh? "
  },
  "409": {
    "speaker": "speaker_1",
    "text": "Why does it happen so often? "
  },
  "410": {
    "speaker": "speaker_0",
    "text": "It doesn't. "
  },
  "411": {
    "speaker": "speaker_1",
    "text": "I feel like it happens a lot. "
  },
  "412": {
    "speaker": "speaker_0",
    "text": "It, it can. "
  },
  "413": {
    "speaker": "speaker_1",
    "text": "Where the plumber's like, \"Oh, okay. Well...\" "
  },
  "414": {
    "speaker": "speaker_0",
    "text": "Exactly. This is in the way. "
  },
  "415": {
    "speaker": "speaker_1",
    "text": "\"This is in my way.\" "
  },
  "416": {
    "speaker": "speaker_0",
    "text": "Yup. \"I have to have fall. Here it is. Here's my fall right through the beam.\" Yeah. So framing inspection can't hap- happen until after MEP inspections. "
  },
  "417": {
    "speaker": "speaker_1",
    "text": "Yup. "
  },
  "418": {
    "speaker": "speaker_0",
    "text": "Um, okay. Temporary dry in underlayment? Temporary dry in. What do you mean temporary? I'm just looking at the scope. On the scope it says, \"Roof system. Temporary dry in measures will be installed.\" Huh. Weird. It shouldn't say that in the scope. That's why this is here, is because of that was written in the scope. It should just be installing underlayment, not temporary dry in. "
  },
  "419": {
    "speaker": "speaker_1",
    "text": "Um."
  },
  "420": {
    "speaker": "speaker_0",
    "text": "So, shingles, that can, that's just one day. Um, just FYI, shingles, whenever we do roofing, uh, pre- uh, up to 6,000 square feet I can do in one day. "
  },
  "421": {
    "speaker": "speaker_2",
    "text": "Mm-hmm. "
  },
  "422": {
    "speaker": "speaker_0",
    "text": "So I can get pretty much any amount of shingling done. "
  },
  "423": {
    "speaker": "speaker_2",
    "text": "Nice. "
  },
  "424": {
    "speaker": "speaker_0",
    "text": "Um, so this can always just say day. Uh, okay, so, \"At the same time, install the flashing, and then install windows and doors.\" So, I would move up my windows and doors to being as soon as the roof is framed. You wanna do that, like, right away, so that way you don't get water in the building in case it rains or something like that. "
  },
  "425": {
    "speaker": "speaker_2",
    "text": "Sure, sure. "
  },
  "426": {
    "speaker": "speaker_0",
    "text": "Does that make sense? "
  },
  "427": {
    "speaker": "speaker_2",
    "text": "Yeah. "
  },
  "428": {
    "speaker": "speaker_0",
    "text": "And then your, your installation, your underlayment should happen in the same time. So you're, like, trying to put in your, your waterproofing and then your windows and doors and your underlayment so the building stays safe. "
  },
  "429": {
    "speaker": "speaker_2",
    "text": "Mm-hmm. "
  },
  "430": {
    "speaker": "speaker_0",
    "text": "Um, then you do your fascia soffit, and then you do your roofing. Or you do roofing first and then your fascia soffit, so that's fine as far as the order goes. Um, and then you can install s- You can install siding as soon as the underlayment is done. It does not have to wait. You know, so the PM might say, \"Okay, I'm gonna use one crew to do all this stuff,\" right? So it's gonna happen in sequence. Or he might say, \"Hey, I'm gonna use this roofer and this siding guy,\" so that way they're gonna happen at the same time. Does that make sense? So, by default, I would just string it, 'cause more than likely we're gonna use the same crew to drive in. I'm not the type of company that brings in a siding guy, and that brings in a roofer, and that br- no, I don't do that, preferably, whenever I can. I just bring in the guy that can do all of it. "
  },
  "431": {
    "speaker": "speaker_2",
    "text": "Sure. "
  },
  "432": {
    "speaker": "speaker_0",
    "text": "Whether it's my crew or my subs, that's pretty much the only way I work. "
  },
  "433": {
    "speaker": "speaker_2",
    "text": "Mm-hmm. "
  },
  "434": {
    "speaker": "speaker_0",
    "text": "If I was doing, if I was a developer, different story, because then I could just have the siding crew go from house to house to house to house to house. Right? Because they're all my houses. "
  },
  "435": {
    "speaker": "speaker_2",
    "text": "Mm-hmm. "
  },
  "436": {
    "speaker": "speaker_0",
    "text": "But with this being what we do, that's how that works. "
  },
  "437": {
    "speaker": "speaker_2",
    "text": "Yep. "
  },
  "438": {
    "speaker": "speaker_0",
    "text": "Just sharing this from industry experience. "
  },
  "439": {
    "speaker": "speaker_2",
    "text": "Perfect. "
  },
  "440": {
    "speaker": "speaker_0",
    "text": "Is that... Okay. "
  },
  "441": {
    "speaker": "speaker_2",
    "text": "Yep, so the siding install happens after windows and doors are in place, right? "
  },
  "442": {
    "speaker": "speaker_0",
    "text": "Yes, windows and doors have to be in place before siding. "
  },
  "443": {
    "speaker": "speaker_2",
    "text": "Yeah. "
  },
  "444": {
    "speaker": "speaker_0",
    "text": "Um, cool. The electrical work can happen as soon as it's framed, all of your MEPs, so you can run the inside MEPs and the outside siding, roofing, fascia, soffit at the same time. "
  },
  "445": {
    "speaker": "speaker_2",
    "text": "Mm-hmm. "
  },
  "446": {
    "speaker": "speaker_0",
    "text": "And that is the most efficient way to do it. "
  },
  "447": {
    "speaker": "speaker_2",
    "text": "Why do you think it didn't do that? "
  },
  "448": {
    "speaker": "speaker_0",
    "text": "On the scope how, why it pulled it this way? "
  },
  "449": {
    "speaker": "speaker_2",
    "text": "It seems like it wanted part of the roofing to be done, like, uh, it delayed it. "
  },
  "450": {
    "speaker": "speaker_0",
    "text": "So this said Milestone dry-in FS. What, what's that mean? "
  },
  "451": {
    "speaker": "speaker_2",
    "text": "Structure dry-in. That, that'd be right there, that diamond. Milestone dry-in. "
  },
  "452": {
    "speaker": "speaker_0",
    "text": "Yeah, so this is tied to the dry-in. This is when it said the dry-in was done. "
  },
  "453": {
    "speaker": "speaker_2",
    "text": "Yeah. "
  },
  "454": {
    "speaker": "speaker_0",
    "text": "But these guys can start working as soon as the windows and doors are in and the underlayment is on. "
  },
  "455": {
    "speaker": "speaker_2",
    "text": "Mm-hmm. "
  },
  "456": {
    "speaker": "speaker_0",
    "text": "They can start working right away. "
  },
  "457": {
    "speaker": "speaker_2",
    "text": "It's a wrong dependency. "
  },
  "458": {
    "speaker": "speaker_0",
    "text": "It's a wrong dependency, yeah. These things, the, the MEPs should be dependent on the underlayment. That's where your pathway needs to be for dependency. Um, the other thing is, generally, you want to do... You, for your MEPs, you wanna do HVAC, then plumbing, then electrical. We, because it's a mini split system, we can do HVAC last, and we should. It should go plumbing, electrical, HVAC, because we're not doing a ducted system. If you're doing the big ducts, you wanna put those in first. (laughs) "
  },
  "459": {
    "speaker": "speaker_2",
    "text": "Mm-hmm. "
  },
  "460": {
    "speaker": "speaker_0",
    "text": "Because those have to go in a certain way. And then your plumbers always bitch at the HVAC people because they wanna get their, they need to get their drain lines in for their fall, right? And then wire, you could throw wire around anything pretty much. "
  },
  "461": {
    "speaker": "speaker_2",
    "text": "Sure. "
  },
  "462": {
    "speaker": "speaker_0",
    "text": "So that's why you wanna do it that way. "
  },
  "463": {
    "speaker": "speaker_2",
    "text": "Mm-hmm. "
  },
  "464": {
    "speaker": "speaker_0",
    "text": "Does that make sense? "
  },
  "465": {
    "speaker": "speaker_2",
    "text": "Mm-hmm. So what was... Sorry, what was the difference between HVAC first or HVAC last "
  },
  "466": {
    "speaker": "speaker_0",
    "text": "If you're doing a ducted system. If you're doing a ducted system, like a traditional heat pump and air handler system, you want HVAC to go first. "
  },
  "467": {
    "speaker": "speaker_2",
    "text": "Oh, okay. "
  },
  "468": {
    "speaker": "speaker_0",
    "text": "If we're doing mini splits, like what we're doing here, you can have them go last. That's fine. "
  },
  "469": {
    "speaker": "speaker_2",
    "text": "Cool. That's, that's in the scope, I'm sure. Yeah, the- "
  },
  "470": {
    "speaker": "speaker_0",
    "text": "What? "
  },
  "471": {
    "speaker": "speaker_2",
    "text": "... the type of duct work or the... "
  },
  "472": {
    "speaker": "speaker_0",
    "text": "Yeah, yeah, because of, uh, H and rough- this says mini split. "
  },
  "473": {
    "speaker": "speaker_2",
    "text": "Mini split, yeah. "
  },
  "474": {
    "speaker": "speaker_0",
    "text": "Yep, rough-in and line set. So yeah, that, that whole thing can be reoriented. But, um, 100 amp subpanel, that's fine, electrical rough-in. So you're saying duration four days on electrical, this duration one and a half days. Yeah, this is probably like a day, but that's fine. It's not a big deal. This can definitely be one guy. The 100 amp subpanel, this can definitely be just one person. And it's just one day. Now, this might have come from my breakdown. You know what I mean? That's probably where it came from, but just FYI. "
  },
  "475": {
    "speaker": "speaker_2",
    "text": "Mm-hmm. "
  },
  "476": {
    "speaker": "speaker_0",
    "text": "Um, electrical rough-in, for sure, the mini split rough-in is just one guy, half a day for the HVAC mini split rough-in. "
  },
  "477": {
    "speaker": "speaker_2",
    "text": "So it gave you three, three and a half. Hmm. "
  },
  "478": {
    "speaker": "speaker_0",
    "text": "Well, it said duration two days. "
  },
  "479": {
    "speaker": "speaker_2",
    "text": "Oh, yeah, two days. "
  },
  "480": {
    "speaker": "speaker_0",
    "text": "'Cause of the holi- or weekend or whatever. "
  },
  "481": {
    "speaker": "speaker_2",
    "text": "Yeah, yeah, yeah. "
  },
  "482": {
    "speaker": "speaker_0",
    "text": "So it gave me two days. You just need, like, half a day, a day maximum. "
  },
  "483": {
    "speaker": "speaker_2",
    "text": "Yeah. "
  },
  "484": {
    "speaker": "speaker_0",
    "text": "Um, plumbing rough-in and supply. It's giving me four days for two guys. That's fine for this kind of job.... extend the vent stacks, that's fine. Put in the tankless rough-in for gas and water, that's fine. Does this have a dependency, plumbing rough-in finish? You probably wanna set the tank before the plumbing rough-in. I'm not super plumbing advanced, personally, but I would want my tank set and know my location, and then tie this stuff in. "
  },
  "485": {
    "speaker": "speaker_1",
    "text": "So would you put tank here and move these forward? "
  },
  "486": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "487": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "488": {
    "speaker": "speaker_0",
    "text": "And, and you could... I would run the tankless and the first day of the plumbing rough-in concurrently. You can run them the same time. "
  },
  "489": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. Okay. "
  },
  "490": {
    "speaker": "speaker_0",
    "text": "Um, and then the rest of that is fine. "
  },
  "491": {
    "speaker": "speaker_1",
    "text": "So, mini-split after the tank? Right. "
  },
  "492": {
    "speaker": "speaker_0",
    "text": "Mini-split can come after your plumbing is done. "
  },
  "493": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "494": {
    "speaker": "speaker_0",
    "text": "And b- because you're doing a mini-split, it's not gonna get in the way of any trades. They can pretty much do it at any time, and it's just gonna take one guy half a day, a day maybe. They're really quick and easy to do. "
  },
  "495": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "496": {
    "speaker": "speaker_0",
    "text": "Um... "
  },
  "497": {
    "speaker": "speaker_3",
    "text": "Does that apply to any type of water heater, or just tankless? So what you were saying, you put it first before the... "
  },
  "498": {
    "speaker": "speaker_0",
    "text": "I would... No, uh, pr- pretty much any tank, I would want it done that way. "
  },
  "499": {
    "speaker": "speaker_3",
    "text": "Okay. "
  },
  "500": {
    "speaker": "speaker_0",
    "text": "You know, to have the... So that way, I know where everything's branching off of. "
  },
  "501": {
    "speaker": "speaker_3",
    "text": "Oh, okay. "
  },
  "502": {
    "speaker": "speaker_0",
    "text": "Does, does that make sense? So I know that- "
  },
  "503": {
    "speaker": "speaker_3",
    "text": "Right. "
  },
  "504": {
    "speaker": "speaker_0",
    "text": "... that, hey, all of these things are gonna come here. "
  },
  "505": {
    "speaker": "speaker_3",
    "text": "Yeah. "
  },
  "506": {
    "speaker": "speaker_0",
    "text": "Um, so your inspections for all of your mechanicals, they all have to be at the same time. They come out, they look at all of the... that work at the same time. "
  },
  "507": {
    "speaker": "speaker_1",
    "text": "What are the things that... So just basically yellow done, blue done, and, uh, I guess there's two colors of blue here? "
  },
  "508": {
    "speaker": "speaker_0",
    "text": "Yeah, light blue and dark blue. "
  },
  "509": {
    "speaker": "speaker_1",
    "text": "Yeah. So all three of those done in one day, three inspections? "
  },
  "510": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "511": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "512": {
    "speaker": "speaker_0",
    "text": "It's the same person, and they look at all three things at the same time. "
  },
  "513": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "514": {
    "speaker": "speaker_0",
    "text": "And then, after they say, \"Okay, you pass,\" or whatever, or, uh, like, I would do... always just budget in them flagging something. You know what I mean? "
  },
  "515": {
    "speaker": "speaker_1",
    "text": "Sure, sure. "
  },
  "516": {
    "speaker": "speaker_0",
    "text": "So I would always... Like, when we do the MEP inspection, whenever that day is, the project manager also has to be there. "
  },
  "517": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "518": {
    "speaker": "speaker_0",
    "text": "Like, 'cause the project manager should really walk through it with the, with the inspector and say... That that way they know specifically. I mean, you get a report, and sometimes you get photos, but a lot of times the inspectors, they have really shitty reports. "
  },
  "519": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "520": {
    "speaker": "speaker_0",
    "text": "So they come, come in. They give you a really shitty report, and then those people also are the ones that never answer the phone. So you try to call them- "
  },
  "521": {
    "speaker": "speaker_1",
    "text": "(laughs) "
  },
  "522": {
    "speaker": "speaker_0",
    "text": "... and be like, \"What's the problem?\" and you can't ever get ahold of them. Yeah, it's a nightmare. So always, by default, you wanna have the project manager there on the day of the mechanical inspection. "
  },
  "523": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. Yeah. "
  },
  "524": {
    "speaker": "speaker_0",
    "text": "Uh, that way you can, you know, take your notes, take your photos, spray paint stuff. "
  },
  "525": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "526": {
    "speaker": "speaker_0",
    "text": "That's what good PMs do. "
  },
  "527": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "528": {
    "speaker": "speaker_0",
    "text": "And then- "
  },
  "529": {
    "speaker": "speaker_1",
    "text": "Save your time. "
  },
  "530": {
    "speaker": "speaker_0",
    "text": "Yeah. So then, after the inspection, expect something to come up, right? And then I would have, probably, depending on the job, anywhere from a two to a four-day, saying, \"No, n- I'm not scheduling any trade after the inspection, because I need to coordinate and get my plumber, my HVAC guy, or my electrician back out here to do their stupid punch list thing.\" "
  },
  "531": {
    "speaker": "speaker_1",
    "text": "Hmm. "
  },
  "532": {
    "speaker": "speaker_0",
    "text": "And then we need to get the inspection done again. "
  },
  "533": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "534": {
    "speaker": "speaker_0",
    "text": "The final, for whatever those MEPs were, and then the inspec... and then the inspector comes out again. "
  },
  "535": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "536": {
    "speaker": "speaker_0",
    "text": "The PM has to go there again. "
  },
  "537": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "538": {
    "speaker": "speaker_0",
    "text": "And then you schedule the framing. "
  },
  "539": {
    "speaker": "speaker_1",
    "text": "And hopefully it's all done- "
  },
  "540": {
    "speaker": "speaker_0",
    "text": "Yes. Exact- "
  },
  "541": {
    "speaker": "speaker_1",
    "text": "... that same, exactly the- "
  },
  "542": {
    "speaker": "speaker_3",
    "text": "So basically, here, you want, like- "
  },
  "543": {
    "speaker": "speaker_0",
    "text": "You, you have this stupid cat-and-mouse game. "
  },
  "544": {
    "speaker": "speaker_3",
    "text": "... all three on Monday, and then have the rest of the week just off- "
  },
  "545": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "546": {
    "speaker": "speaker_3",
    "text": "... and relax. "
  },
  "547": {
    "speaker": "speaker_0",
    "text": "Yes. And this is where inefficiencies happen, FYI. When you have... R- Remember when I was saying yesterday that, like, field crew like to piddle? "
  },
  "548": {
    "speaker": "speaker_3",
    "text": "Mm-hmm. "
  },
  "549": {
    "speaker": "speaker_0",
    "text": "When we have scheduled for, for inspections and stuff like that, my guys are still there. "
  },
  "550": {
    "speaker": "speaker_3",
    "text": "Right. "
  },
  "551": {
    "speaker": "speaker_0",
    "text": "And I need my project managers to do a better job and pull them off. That's why I need the PEP. That's why I need the gantt chart. "
  },
  "552": {
    "speaker": "speaker_3",
    "text": "Mm-hmm. "
  },
  "553": {
    "speaker": "speaker_0",
    "text": "Um, so, yeah. So I would schedule, like, nothing for that week, like you said. If it was a Monday, schedule nothing for four days. Plan on trying to get whatever punch list shows up, and, uh, get your trades back out there to handle that stuff. Then they come back and do the MEP inspection again, and then you go and do your framing inspection. Mo-... Sometimes, you can get the inspector to do the framing inspection at the second mechanical, but not always. "
  },
  "554": {
    "speaker": "speaker_3",
    "text": "Hmm. "
  },
  "555": {
    "speaker": "speaker_0",
    "text": "It depends on the inspector. Some inspectors... Inspectors are qualified to do different kinds of inspections. And if you have one inspector that has all of them, he'll- "
  },
  "556": {
    "speaker": "speaker_3",
    "text": "Mm-hmm. "
  },
  "557": {
    "speaker": "speaker_0",
    "text": "... just do it, right? "
  },
  "558": {
    "speaker": "speaker_3",
    "text": "Yeah. "
  },
  "559": {
    "speaker": "speaker_0",
    "text": "He'll do your framing right then and there. But if that inspector doesn't have framing, isn't qualified for framing by, you know, their... the city or the municipality, then they have to call on the, the other guy to do the framing. "
  },
  "560": {
    "speaker": "speaker_3",
    "text": "Mm-hmm. "
  },
  "561": {
    "speaker": "speaker_0",
    "text": "That's how that works. "
  },
  "562": {
    "speaker": "speaker_3",
    "text": "Mm-hmm. "
  },
  "563": {
    "speaker": "speaker_0",
    "text": "Um, so, yeah. Do nothing. Get another inspection the following Monday. Hopefully it passes for all your MEPs. Then you need to schedule your framing inspection. And then there's probab-... I would schedule another two or three days of lull while you get your framer back to do some punch list work. And then schedule a final framing, and now you're good. "
  },
  "564": {
    "speaker": "speaker_3",
    "text": "Yeah. "
  },
  "565": {
    "speaker": "speaker_0",
    "text": "And then, after that, you do all of your insulation. So when your rough-in mechanical, I want my insulation to show up. Like, the day that the inspector is supposed to do the, the inspections is the day, the same day that I want all my insulation material to show up. "
  },
  "566": {
    "speaker": "speaker_3",
    "text": "Okay. "
  },
  "567": {
    "speaker": "speaker_0",
    "text": "Because then you go through this, you know, week, two-week period of punch list and bullshit from all your framers and your mechanicals. After that, you do... You have one day for your crew, pretty much, to do all the insulation, and then you need to do an insulation inspection. "
  },
  "568": {
    "speaker": "speaker_3",
    "text": "Yep, we just have it ready to go. "
  },
  "569": {
    "speaker": "speaker_0",
    "text": "Yeah, exactly. That's why I want it when th- when I schedule the MEPs. Like, when that inspection is, you wanna have those materials. "
  },
  "570": {
    "speaker": "speaker_3",
    "text": "Yeah. So when you say installation, that's the same as a framing inspector, right "
  },
  "571": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "572": {
    "speaker": "speaker_3",
    "text": "All right. "
  },
  "573": {
    "speaker": "speaker_0",
    "text": "Yes. But they can't do both at the same time, 'cause obviously they need to inspect the framing before you put the insulation on. Then you put the insulation up. Then they look at it. "
  },
  "574": {
    "speaker": "speaker_3",
    "text": "Got it, got it. Okay."
  },
  "575": {
    "speaker": "speaker_0",
    "text": "Um, yeah. So that's fine on all this stuff. So after... I personally would... How I would treat this Gantt chart, I would pencil out all that stuff. Pretty much everybody has a hard date, except for my drywall crew, and later. "
  },
  "576": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "577": {
    "speaker": "speaker_0",
    "text": "Because I don't know how long it's gonna take me to get through all these inspections and all this BS. "
  },
  "578": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "579": {
    "speaker": "speaker_0",
    "text": "And because there's too many variables, I would, like, pencil in my drywall crew, but I would start calling them to get them out there after I pass my insulation, obviously. "
  },
  "580": {
    "speaker": "speaker_1",
    "text": "Right. Uh- "
  },
  "581": {
    "speaker": "speaker_0",
    "text": "So I would ca- Actually, I take that back. I would call my drywall crew when I've scheduled the first insulation inspection. "
  },
  "582": {
    "speaker": "speaker_1",
    "text": "Sure, sure. "
  },
  "583": {
    "speaker": "speaker_0",
    "text": "Because insula- in- insulation inspections pretty much always pass. "
  },
  "584": {
    "speaker": "speaker_1",
    "text": "So- "
  },
  "585": {
    "speaker": "speaker_0",
    "text": "They're like y- you- you have to be a dumbass to fail at an insulation inspection. "
  },
  "586": {
    "speaker": "speaker_1",
    "text": "(laughs) "
  },
  "587": {
    "speaker": "speaker_0",
    "text": "Or the inspector hates you for some reason. "
  },
  "588": {
    "speaker": "speaker_1",
    "text": "So basically- "
  },
  "589": {
    "speaker": "speaker_0",
    "text": "(laughs) "
  },
  "590": {
    "speaker": "speaker_1",
    "text": "... (laughs) you'd have all three of those, those tests up above on that Monday, and you'd schedule the week off. "
  },
  "591": {
    "speaker": "speaker_0",
    "text": "Yep. "
  },
  "592": {
    "speaker": "speaker_1",
    "text": "And you'd push this to the next week. But when would you hear back about those inspections? I missed that. Like all- "
  },
  "593": {
    "speaker": "speaker_0",
    "text": "Same day. "
  },
  "594": {
    "speaker": "speaker_1",
    "text": "Same day. "
  },
  "595": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "596": {
    "speaker": "speaker_1",
    "text": "So you, in theory- "
  },
  "597": {
    "speaker": "speaker_0",
    "text": "And, and that's also why you want the project manager to be there with the inspector. Not only to take his feedback- "
  },
  "598": {
    "speaker": "speaker_1",
    "text": "Right. "
  },
  "599": {
    "speaker": "speaker_0",
    "text": "But he'll just tell you verbally. He's like, \"You're good. Go ahead. I'll put the paperwork when I get back in the office, but go ahead and schedule your shift.\" "
  },
  "600": {
    "speaker": "speaker_1",
    "text": "So in theory, you have a second round of inspections that might happen Thursday, Friday. And as soon as all three pass, you (snaps fingers) immediately start penciling and drywall. Yep? "
  },
  "601": {
    "speaker": "speaker_0",
    "text": "Yes. As soon as I am scheduling my insulation inspection, I'm saying, \"Drywaller, you need to be out here next Thursday,\" right? Because I know today is Monday, and I'm, and I just passed this. "
  },
  "602": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "603": {
    "speaker": "speaker_0",
    "text": "Tomorrow, I'm gonna get my insulation installed. Wednesday, I'm gonna have that inspection again for the insulation inspection, and Thursday, Mr. Drywall Man needs to be there. "
  },
  "604": {
    "speaker": "speaker_1",
    "text": "Right. So do you s- "
  },
  "605": {
    "speaker": "speaker_0",
    "text": "You can have a couple lag days if you want, but I... Not me. I wouldn't, because the insulation inspection, like I said- "
  },
  "606": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "607": {
    "speaker": "speaker_0",
    "text": "... they have to, like, hate you to fail you. "
  },
  "608": {
    "speaker": "speaker_1",
    "text": "Sure. So we can, we can basically hard date all the way through the second round of inspections, installation, and this test, and from here on, it's up in the air, then? "
  },
  "609": {
    "speaker": "speaker_0",
    "text": "Yes. It's like you don't know when your drywaller will start, but, uh, like, how long the drywall takes and how long all the other trades take, all that is gonna be the same. It's just that start date is, is the most unknown start date. "
  },
  "610": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "611": {
    "speaker": "speaker_0",
    "text": "Because of inspections. "
  },
  "612": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "613": {
    "speaker": "speaker_0",
    "text": "After you get past your insulation inspection, there is nothing until the building is completely done. You only have a final, and it's a final for everything. It's al- "
  },
  "614": {
    "speaker": "speaker_1",
    "text": "Right. "
  },
  "615": {
    "speaker": "speaker_0",
    "text": "They... Then they just basically come in and look at your outlets, make sure you have cover plates, you know what I mean? They make sure your switches turn the lights on, like, crap. "
  },
  "616": {
    "speaker": "speaker_1",
    "text": "Sure. "
  },
  "617": {
    "speaker": "speaker_0",
    "text": "You know, they make sure no, no faucets are leaking, no HVAC is hissing. "
  },
  "618": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "619": {
    "speaker": "speaker_0",
    "text": "Um, cool. So then you do your drywall. "
  },
  "620": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "621": {
    "speaker": "speaker_0",
    "text": "Hang it, tape it, sand it. That's fine. You can combine all these into one phase. They don't need to be three separate. You can just say drywall to level three finish and then make this whole thing one continuous bar. "
  },
  "622": {
    "speaker": "speaker_1",
    "text": "Looks like it gave 11 days. It has five plus four plus two for the whole phase. "
  },
  "623": {
    "speaker": "speaker_0",
    "text": "Yeah. "
  },
  "624": {
    "speaker": "speaker_1",
    "text": "Or the whole component. Uh... "
  },
  "625": {
    "speaker": "speaker_0",
    "text": "That's probably about right. "
  },
  "626": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "627": {
    "speaker": "speaker_0",
    "text": "I mean, maybe nine days. 11 is gonna be on the high end- "
  },
  "628": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "629": {
    "speaker": "speaker_0",
    "text": "... to me, on this kind of job. Um, priming, walls and ceilings, yep, you can run through this in a day or two. That's no problem. Apply two coats of finish paint. This is gonna take longer. Um, no, you get your two coats of finish paint. (sighs) I go through and I prime... My process is... And another PM might be- do this a little differently, but we can set this as a standard rule and then they can modify it if they want to. What I like to do for a project like this, I run through as soon as drywall is done and I spray all my walls and ceilings and maybe I back roll, depending on the job and the finish. But I'll spray all my walls and ceilings to get my primer up, and that same day, I will, I'll do that, like, early in the morning. I'd take lunch, I'd come back, and then I would go ahead and spray and roll, uh, my finish coat for my ceilings. So all my priming is done on the entire building and my ceilings are finished. "
  },
  "630": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "631": {
    "speaker": "speaker_0",
    "text": "Depending on the job, I might go ahead and s- and do my first coat of rolling on the walls only, because I have other trades come in, like tile guys, floor guys, and stuff like that to finish carpenters, and they always put their hands on the walls. "
  },
  "632": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "633": {
    "speaker": "speaker_0",
    "text": "So they fucking make the paint job look like shit. "
  },
  "634": {
    "speaker": "speaker_1",
    "text": "Yep. (laughs) "
  },
  "635": {
    "speaker": "speaker_0",
    "text": "So it's kind of crew dependent and who you have doing it. Like, if it's our in-house crew- "
  },
  "636": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "637": {
    "speaker": "speaker_0",
    "text": "... I'm super confident. But if it's a sub, who knows? "
  },
  "638": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "639": {
    "speaker": "speaker_0",
    "text": "You know? Um, so at most, I'll finish my ceilings, get all my walls and stuff primed, and at most I'll roll one coat only on my walls. I won't cut it in and I won't do any of that. "
  },
  "640": {
    "speaker": "speaker_1",
    "text": "Gotcha. "
  },
  "641": {
    "speaker": "speaker_0",
    "text": "Okay? "
  },
  "642": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "643": {
    "speaker": "speaker_0",
    "text": "So do with, with that what you will. "
  },
  "644": {
    "speaker": "speaker_1",
    "text": "(laughs) "
  },
  "645": {
    "speaker": "speaker_0",
    "text": "Um, but that's just me. And then I would do all my finish painting at the end, all my cutting, and at least one more roll on the walls. But the ceilings are usually good. The only time is if you get a really messy electrician and he'll leave fingerprints on my finished ceiling paint around all the cam lights- "
  },
  "646": {
    "speaker": "speaker_1",
    "text": "(laughs) "
  },
  "647": {
    "speaker": "speaker_0",
    "text": "... and stuff like that. But, uh, but my electricians, I don't really sub electrical work. They're pretty much always Warren and, and my guys, and, uh, they're really well trained to not do that, so. "
  },
  "648": {
    "speaker": "speaker_1",
    "text": "Sure. "
  },
  "649": {
    "speaker": "speaker_0",
    "text": "And that's also why I like having my own electricians, because electricians are messy. Okay. There's a few back...... oh, did I miss something? Oh, way back here? "
  },
  "650": {
    "speaker": "speaker_1",
    "text": "I don't know what they're depending on. "
  },
  "651": {
    "speaker": "speaker_0",
    "text": "What is this? "
  },
  "652": {
    "speaker": "speaker_1",
    "text": "Depends on the item. "
  },
  "653": {
    "speaker": "speaker_0",
    "text": "\"Remove existing window frame opening insulate.\" Drywall, patch, paint. Oh, okay. Um, remove existing window frame opening and insulate. I think that is ... I'll show you what that is on the plans here. There's a window in this bathroom right now. "
  },
  "654": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "655": {
    "speaker": "speaker_0",
    "text": "And that window obviously is gonna go away because of this addition here. That's what that work is. It's retro work. "
  },
  "656": {
    "speaker": "speaker_1",
    "text": "Right. "
  },
  "657": {
    "speaker": "speaker_0",
    "text": "I would do that retro work, all of these. Okay, so these two, remove the existing window frame and the drywall and finish the, do all the hall patching, I'd do all of that at the same time when I'm doing the drywall. So these items would be tied to the drywall. "
  },
  "658": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "659": {
    "speaker": "speaker_0",
    "text": "This item, remove the acrylic shower insert and replace it, the customer wanted that done before we even broke ground on the job. "
  },
  "660": {
    "speaker": "speaker_1",
    "text": "Hm. Uh- "
  },
  "661": {
    "speaker": "speaker_0",
    "text": "Okay? So that would ha- "
  },
  "662": {
    "speaker": "speaker_1",
    "text": "... that's right. "
  },
  "663": {
    "speaker": "speaker_0",
    "text": "That would have to happen, like, when we're moving those HVAC units and stuff. When we're... Oh, it was in demo, I think. Where, where is that HVAC? Yeah, this. I want that shower to be replaced somewhere in here. So, like, the- I would just have them do that at the same time. "
  },
  "664": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "665": {
    "speaker": "speaker_0",
    "text": "So that way the customer had a fresh shower before we started this job. That's what they want. "
  },
  "666": {
    "speaker": "speaker_1",
    "text": "So it's kind of like a non-standard type of rule set. "
  },
  "667": {
    "speaker": "speaker_0",
    "text": "Yes, yes. "
  },
  "668": {
    "speaker": "speaker_1",
    "text": "You know? "
  },
  "669": {
    "speaker": "speaker_0",
    "text": "Yeah. I think, uh, I think talking about this out loud and making rule sets and stuff, I would also ... Like, we're gonna have a ton of rules. It's like, you gotta run through this school of thought, you gotta run through this school of thought. "
  },
  "670": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "671": {
    "speaker": "speaker_0",
    "text": "'Cause that's literally how you do this. "
  },
  "672": {
    "speaker": "speaker_1",
    "text": "Yup. "
  },
  "673": {
    "speaker": "speaker_0",
    "text": "One of them is, like, what's the retro work? "
  },
  "674": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "675": {
    "speaker": "speaker_0",
    "text": "What's retro work versus new work? "
  },
  "676": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "677": {
    "speaker": "speaker_0",
    "text": "Does that make sense? "
  },
  "678": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "679": {
    "speaker": "speaker_0",
    "text": "Like, that's gonna have to be a rule set. "
  },
  "680": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "681": {
    "speaker": "speaker_0",
    "text": "And then, e- maybe that ... You could have that ... Inside of that, have customer requests, but there should probably be a separate rule set for saying, \"Hey, what are the customer requests? What are the things that we're gonna do to accommodate the customer during the project?\" "
  },
  "682": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "683": {
    "speaker": "speaker_0",
    "text": "Right? And say, \"Okay, the customer requested that we take care of this, this, and this-\" "
  },
  "684": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "685": {
    "speaker": "speaker_0",
    "text": "\"... before we start.\" "
  },
  "686": {
    "speaker": "speaker_1",
    "text": "It's that exception to the rule. "
  },
  "687": {
    "speaker": "speaker_0",
    "text": "So that, their experience ... Exactly. That way, their experience is good. Does that make sense? "
  },
  "688": {
    "speaker": "speaker_1",
    "text": "Yeah. Yeah. It's, uh ... I mean, th- yeah, they should be treated differently, and that does, like, complicate things but, but, um, as long as you're really explicit about what's, what's, like, n- stuff that's going up that's new and stuff that's being adjusted or stuff that's existing, then ... "
  },
  "689": {
    "speaker": "speaker_0",
    "text": "Yeah. Well, so when you read the scope of work, right, and when you read specifically the objective, like how to make this a little bit easier, the objective just says, \"Two story addition, 30 by 10, expansion of a primary bedroom, master bathroom, and walk-in closet.\" Those, that's what the addition is. Nowhere did I talk about a hallway except for when we brought up this line. This window, right? Remove an existing window. That's always retro work- "
  },
  "690": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "691": {
    "speaker": "speaker_0",
    "text": "... because it's existing. "
  },
  "692": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "693": {
    "speaker": "speaker_0",
    "text": "Right? So that's something that you could use to flag it. "
  },
  "694": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "695": {
    "speaker": "speaker_0",
    "text": "If you, you, say the word existing, check if it's retro work. Does that make sense? "
  },
  "696": {
    "speaker": "speaker_1",
    "text": "Sure. "
  },
  "697": {
    "speaker": "speaker_0",
    "text": "You can, you could put a check there- "
  },
  "698": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "699": {
    "speaker": "speaker_0",
    "text": "... a- as far as the programming on it. "
  },
  "700": {
    "speaker": "speaker_1",
    "text": "Yup. "
  },
  "701": {
    "speaker": "speaker_0",
    "text": "Um, and then when it says hall, so drywall, finish, paint hall patches, well, this objective didn't say anything about a hallway. "
  },
  "702": {
    "speaker": "speaker_1",
    "text": "Hm. "
  },
  "703": {
    "speaker": "speaker_0",
    "text": "So that must be retro work. "
  },
  "704": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "705": {
    "speaker": "speaker_0",
    "text": "Right? So it's like, if it's part of an addition and part of ... Like, read what the addition is, and then if we're referencing scope of work that's not a component of this addition, then flag it that it could be retrofit, retro work, and the PM needs to ... It needs to ask the PM. "
  },
  "706": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "707": {
    "speaker": "speaker_0",
    "text": "Right? And then that's, that's how you push through that. "
  },
  "708": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "709": {
    "speaker": "speaker_0",
    "text": "Sure. Um, and then, yeah, this is a customer request item, right? So this is gonna happen way before. Does that make sense? "
  },
  "710": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "711": {
    "speaker": "speaker_0",
    "text": "So then, tha- that is just gonna have to be an open-ended question that's prompted by the user. Like, this is a customer request. Or I can always look at modifying the scope of work or even adding a supplemental document, if you guys want. "
  },
  "712": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "713": {
    "speaker": "speaker_0",
    "text": "I'm open to that too. Like, one of the things the salespeople have to do when they close out a job, they have to move the proposal, which has the scope of work in it, and then they can ... We already do a multi-question thing. When you move a job in HubSpot from, uh, to closed one, like, we won the job, it asks you, like, 15 or 20 questions. "
  },
  "714": {
    "speaker": "speaker_1",
    "text": "Hm. "
  },
  "715": {
    "speaker": "speaker_0",
    "text": "Right? Just so that way it preps the ops team- "
  },
  "716": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "717": {
    "speaker": "speaker_0",
    "text": "... for what they need to do. And as part of that, we can say, \"Hey, we need a, the salesperson to write a report specifically about customer requests.\" "
  },
  "718": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "719": {
    "speaker": "speaker_0",
    "text": "Right? So that way you always automatically have this input the same. You know what I mean? "
  },
  "720": {
    "speaker": "speaker_1",
    "text": "For sure. "
  },
  "721": {
    "speaker": "speaker_0",
    "text": "And then you can have the PM do it too, and say ... Like, you have one from sales to say, \"Hey, these are the customer requests for the PM to start going through,\" and then as the PM walks through the job with the customer, goes through the selections and design, one of the steps that he can do is fill out something to help with that in the future. Does that make sense? "
  },
  "722": {
    "speaker": "speaker_1",
    "text": "Yeah. That's one of the best improvements that could be made- "
  },
  "723": {
    "speaker": "speaker_0",
    "text": "Yeah, for sure. "
  },
  "724": {
    "speaker": "speaker_1",
    "text": "... because the rules, hopefully, like, just from having you go over, like, example over example, the rules will start to fill out, but- "
  },
  "725": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "726": {
    "speaker": "speaker_1",
    "text": "... the more context we can give going in- "
  },
  "727": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "728": {
    "speaker": "speaker_1",
    "text": "... for this specific project, the better at, the output will be- "
  },
  "729": {
    "speaker": "speaker_0",
    "text": "Exactly. "
  },
  "730": {
    "speaker": "speaker_1",
    "text": "... every time. "
  },
  "731": {
    "speaker": "speaker_0",
    "text": "Exactly. And that's why, like, that's why we wanted to do it this way, right? "
  },
  "732": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "733": {
    "speaker": "speaker_0",
    "text": "So I could flush out all these rules with you guys. Um, okay. So that's a customer-specific item. Again, before we do the inputs, we can make that a requirement. Um, PVC, patch, trim. Yeah, so this is part of this. "
  },
  "734": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "735": {
    "speaker": "speaker_0",
    "text": "So that's fine. Um-And again, we understand that these have to move in the timeline. The, these two items, the existing window and framing, and this can go in when we're doing the drywall, and then this item is gonna have to happen before we start the job. So, custom shower and waterproofing. Its dependency is drywall is finished, which is definitely true, but it also is dependent on procurement of tile. Where is that? Is, d- you see this? "
  },
  "736": {
    "speaker": "speaker_1",
    "text": "Um, I would assume it's up at the beginning of the list. "
  },
  "737": {
    "speaker": "speaker_0",
    "text": "Okay, so this is a bundled thing with some of the material ordered? "
  },
  "738": {
    "speaker": "speaker_1",
    "text": "Yeah, I think it was its own line at the top. The very, like, literally one of the first things. "
  },
  "739": {
    "speaker": "speaker_0",
    "text": "Was tile? Or is it part of selections? "
  },
  "740": {
    "speaker": "speaker_1",
    "text": "P- procure... order tile? Um, did you ever kind of order tile to see what it's called? Uh, kind, procurement, I think that's it. "
  },
  "741": {
    "speaker": "speaker_0",
    "text": "Probably. So saying, hey, if this was done at any time, and the drywall is done, then I can do this. Which makes sense why it's pathed there. I like that. I like that it's dependent on both those items. That's actually something I didn't think of, but that's actually really good. "
  },
  "742": {
    "speaker": "speaker_1",
    "text": "Cool. "
  },
  "743": {
    "speaker": "speaker_0",
    "text": "This is just a one-day thing. Don't know if that matters for you right now. Again, it might co- it might have came from the breakdown. Um, shower bench mosaic, tile, niche. Yep, we can do that just fine. LVT. Okay, so this, the, the flooring says it's dependent on the finished paint. That sh- that's not, that w- that should not be the case. We should do the flooring, we should do the flooring, um, after the walls are primed. So you can run the shower and the flooring concurrently if you want to. Actually, I take that back. Let's do the shower first. "
  },
  "744": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "745": {
    "speaker": "speaker_0",
    "text": "Let's do the shower first and then start flooring. "
  },
  "746": {
    "speaker": "speaker_1",
    "text": "Completely? "
  },
  "747": {
    "speaker": "speaker_0",
    "text": "Once le- no, once the pan is set. "
  },
  "748": {
    "speaker": "speaker_1",
    "text": "Okay, so that, so has, like, uh... "
  },
  "749": {
    "speaker": "speaker_0",
    "text": "So this dependency could just be this pan being done. "
  },
  "750": {
    "speaker": "speaker_1",
    "text": "Right. Gotcha. Okay, and then tile and install, LVT will overlap. "
  },
  "751": {
    "speaker": "speaker_0",
    "text": "Yes. Yeah, these t- two things are fine to overlap. Um, electrical trim-out, this has a dependency on paint finish. That's also not true. Um, I would put this in after the primer is done, um, but you can't have too many trades tripping over each other either. So there probably needs to be something along with the finish work that says, like, probably b- should be a question for the PM to say, \"How many trades can run in this interior finish space at the same time, maximum, at any given point?\" "
  },
  "752": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "753": {
    "speaker": "speaker_0",
    "text": "And I would say two. "
  },
  "754": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "755": {
    "speaker": "speaker_0",
    "text": "You know? "
  },
  "756": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "757": {
    "speaker": "speaker_0",
    "text": "Um, so that way, it'll, that's another set of rules that it's going to have to follow, right? "
  },
  "758": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "759": {
    "speaker": "speaker_0",
    "text": "Because all these things can happen at the same time, but they shouldn't happen at the same time. Make sense? "
  },
  "760": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "761": {
    "speaker": "speaker_0",
    "text": "So I would, I would set that as a rule, that two interior finish trades can be happening at the same time. So with that being said, that's gonna cover your LVT, your electrical, your mini s- your mini split finish, all that stuff, right? All this stuff is just gonna kind of happen in sequence, and it doesn't really matter. It, the real thing that matters is getting it, all of it done in a certain period of time. "
  },
  "762": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "763": {
    "speaker": "speaker_0",
    "text": "Like, if we pencil this out and it's seven days, as long as PM got it done in seven days, I'm good with it. "
  },
  "764": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "765": {
    "speaker": "speaker_0",
    "text": "I don't really give a shit when and which trade goes when, you know? "
  },
  "766": {
    "speaker": "speaker_1",
    "text": "Sure. "
  },
  "767": {
    "speaker": "speaker_0",
    "text": "Um, plumbing, trim, vanity, shower hookups, yep, this is 100% true. Bath shower has to be done, LVT flooring has to be done, and the cabinets have to be done. Um, install this, yes, depends on the flooring, and yes, depends on the procurement. Um, install interior doors, baseboards and casings. Uh, that has to be done after flooring, not paint. After my flooring is done, then I can do all this stuff. The painting, the finish painting should really be at the end. You kind of have two phases of painting. You have paint one and paint two. "
  },
  "768": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "769": {
    "speaker": "speaker_0",
    "text": "Just like electrical has rough-in and finish, paint one happens as soon as you're, you're done with drywall, with your priming, finish ceilings and possibly sealing, or roll-on rolls, and then paint two, the final, final is gonna happen after. "
  },
  "770": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "771": {
    "speaker": "speaker_0",
    "text": "So this thing just blanked or something, so ******. "
  },
  "772": {
    "speaker": "speaker_1",
    "text": "It's still done. "
  },
  "773": {
    "speaker": "speaker_0",
    "text": "Okay, cool. "
  },
  "774": {
    "speaker": "speaker_1",
    "text": "Um, why not have all painting at the end if you have to split it? "
  },
  "775": {
    "speaker": "speaker_0",
    "text": "Because, uh, priming it will seal all the drywall dust back. "
  },
  "776": {
    "speaker": "speaker_1",
    "text": "Oh, okay. "
  },
  "777": {
    "speaker": "speaker_0",
    "text": "So as people move and operate in the space, they can track it through the rest of the customer's house. "
  },
  "778": {
    "speaker": "speaker_1",
    "text": "Yeah, yeah, yeah. "
  },
  "779": {
    "speaker": "speaker_0",
    "text": "And do all kinds of other stuff like that. So that's why you wanna do paint one first. "
  },
  "780": {
    "speaker": "speaker_1",
    "text": "Gotcha. "
  },
  "781": {
    "speaker": "speaker_0",
    "text": "Um, caulking fill and stuff like that, yep, has to be done after you finish carpentry work. What is this? Electrical final. Um, okay, so my closeout... Substantial completion. The diamond is a what? Is a checkpoint? "
  },
  "782": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "783": {
    "speaker": "speaker_0",
    "text": "Okay, so substantial completion should happen right after paint two.That's when it's substantially complete. And then, I would do my punch list and paint touch-ups. So I would separate this out into two steps: I would do the punch list, like, there needs to be a checkpoint after paint two, or it can happen before paint two, but I would say for sure by then- "
  },
  "784": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "785": {
    "speaker": "speaker_0",
    "text": "... we need to have the PM do a walkthrough with the homeowner for a punch list. And I have a form that's in every single job folder. "
  },
  "786": {
    "speaker": "speaker_1",
    "text": "(clears throat) "
  },
  "787": {
    "speaker": "speaker_0",
    "text": "That's the- "
  },
  "788": {
    "speaker": "speaker_1",
    "text": "Nice. "
  },
  "789": {
    "speaker": "speaker_0",
    "text": "... an SOP to fill out. And what happens is, read through the SOP for what to do on how to d- do a punch list with Tri-Cities, you walk through with the homeowner, you have to take photos of the specific thing, that you have to write out... there's like a whole bunch of blank lines you physically write out. Uh, these are the punch list items, here I documented it, I uploaded it as a data log, I labeled it this way. And then once all the items are filled out saying this is the punch list, before you leave with the customer, you have the customer sign it. "
  },
  "790": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "791": {
    "speaker": "speaker_0",
    "text": "So that way they say, \"Yes, I agree with these are the punch list items.\" And the reason we do that is some customers they just keep going, and going, and going. And you do the punch list and then they find more stuff and it's like, \"No, we have to draw a line somewhere.\" "
  },
  "792": {
    "speaker": "speaker_1",
    "text": "(clears throat) "
  },
  "793": {
    "speaker": "speaker_0",
    "text": "That's what this is for. "
  },
  "794": {
    "speaker": "speaker_1",
    "text": "Yeah. "
  },
  "795": {
    "speaker": "speaker_0",
    "text": "And then I- I tell the PMs, I'm like, \"Be very frank with them. We're not doing this again after they sign this.\" "
  },
  "796": {
    "speaker": "speaker_1",
    "text": "Mm-mm. "
  },
  "797": {
    "speaker": "speaker_0",
    "text": "You know what I mean? So g- take as much time as you need, you know, and the PM is going to walk through diligently with them. And one of the things that I tell the PMs to do, they're trained to do this, I'm like, \"You must point out at least two things that the customer didn't see.\" "
  },
  "798": {
    "speaker": "speaker_1",
    "text": "Mm. Mm. "
  },
  "799": {
    "speaker": "speaker_0",
    "text": "Because you're the construction guy, you're going to see more stuff than they do. I always do. "
  },
  "800": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "801": {
    "speaker": "speaker_0",
    "text": "And, uh, that, it helps build trust and faith. "
  },
  "802": {
    "speaker": "speaker_1",
    "text": "Totally. "
  },
  "803": {
    "speaker": "speaker_0",
    "text": "And if there's a little bit of stuff that the customer is concerned with at the end after we packed up and left, that's fine. That's why I do one-year warranty. You know what I mean? "
  },
  "804": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. "
  },
  "805": {
    "speaker": "speaker_0",
    "text": "I'll come back and do stuff like that. Especially with additions. Every single addition that we build always has drywall cracking. Every single one of them. Above the doors, windows, or headers, and stuff like that- "
  },
  "806": {
    "speaker": "speaker_1",
    "text": "Mm. "
  },
  "807": {
    "speaker": "speaker_0",
    "text": "Beca- and some inside scenes. Because when you build something like this, nothing is settled. "
  },
  "808": {
    "speaker": "speaker_1",
    "text": "Oh, yeah. "
  },
  "809": {
    "speaker": "speaker_0",
    "text": "You know what I mean? Like, your studs when you cut them, you know, there's an eighth inch off here, there's a 16th inch off here. When that drywall settles and it caused drywall cracking, we come back and we take care of that for free. That's part of our jobs. "
  },
  "810": {
    "speaker": "speaker_1",
    "text": "Cool. "
  },
  "811": {
    "speaker": "speaker_0",
    "text": "You know. Um, so yeah. The substantially complete is after paint two is done, and that's not dependent on punch list. A punch list is after substantially complete. "
  },
  "812": {
    "speaker": "speaker_1",
    "text": "Yep. "
  },
  "813": {
    "speaker": "speaker_0",
    "text": "Um, then you do the punch list, and then you do your pa- then you s- I would schedule your paint touch-ups. Because if we're using subs and stuff, they're probably left. If we're using our crew, they might be there, but I would sched- I would just plan the default is to schedule it. "
  },
  "814": {
    "speaker": "speaker_1",
    "text": "Okay. So the substantially complete right here on that Friday, after the paint two is done- "
  },
  "815": {
    "speaker": "speaker_0",
    "text": "Yep. "
  },
  "816": {
    "speaker": "speaker_1",
    "text": "... the inspection is good? "
  },
  "817": {
    "speaker": "speaker_0",
    "text": "The inspection you can do at that same time. "
  },
  "818": {
    "speaker": "speaker_1",
    "text": "Okay. "
  },
  "819": {
    "speaker": "speaker_0",
    "text": "When you're substantially complete and when your, you know, your paint job and stuff. "
  },
  "820": {
    "speaker": "speaker_1",
    "text": "There's three inspections here. "
  },
  "821": {
    "speaker": "speaker_0",
    "text": "But they all happen th- by the same person the same day. "
  },
  "822": {
    "speaker": "speaker_1",
    "text": "Same day, okay. "
  },
  "823": {
    "speaker": "speaker_0",
    "text": "Just like all my regular MEPs. "
  },
  "824": {
    "speaker": "speaker_1",
    "text": "Nice. So you schedule that, uh, substantially complete or before "
  },
  "825": {
    "speaker": "speaker_0",
    "text": "You schedule it, you schedule that inspection when paint two is supposed to be done. "
  },
  "826": {
    "speaker": "speaker_1",
    "text": "Yep. Same as the walkthrough or the, the substantially complete "
  },
  "827": {
    "speaker": "speaker_0",
    "text": "Yes. "
  },
  "828": {
    "speaker": "speaker_1",
    "text": "And then you give it, like, another week for handling the final touch-ups from the punch list? "
  },
  "829": {
    "speaker": "speaker_0",
    "text": "Yeah, it's dependent on the project, um, but anywhere between one and three days. "
  },
  "830": {
    "speaker": "speaker_1",
    "text": "Okay. Then- "
  },
  "831": {
    "speaker": "speaker_0",
    "text": "Is- is typical punch list. "
  },
  "832": {
    "speaker": "speaker_1",
    "text": "Then you're done? "
  },
  "833": {
    "speaker": "speaker_0",
    "text": "Then you're done. "
  },
  "834": {
    "speaker": "speaker_1",
    "text": "Nice. "
  },
  "835": {
    "speaker": "speaker_0",
    "text": "That's the job. "
  },
  "836": {
    "speaker": "speaker_1",
    "text": "Well, that was simple. (laughs) "
  },
  "837": {
    "speaker": "speaker_0",
    "text": "(laughs) Now, do this times my- I have 11 active projects right now with my two PMs. So there, one, one guy's running six of these, and one is running five. "
  },
  "838": {
    "speaker": "speaker_1",
    "text": "Mm-hmm. Yeah. Um, well, yeah, I think, I think we should talk more about what inputs would be really valuable to have like as a routine for these. I think that would make a huge difference, but- "
  },
  "839": {
    "speaker": "speaker_0",
    "text": "Do you, do you want to stop this recording and then restart it? So that we can say, \"Hey, this recording is working.\" "
  },
  "840": {
    "speaker": "speaker_1",
    "text": "Yeah, yeah."
  }
}
