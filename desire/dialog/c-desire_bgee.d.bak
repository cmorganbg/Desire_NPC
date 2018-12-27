
/* Initialize dialogue files */
BEGIN ~C-DESIRE~
BEGIN ~C-DESIRP~
BEGIN ~C-DESIRJ~
BEGIN ~C-DESIRB~

APPEND ~C-DESIRE~

IF ~StateCheck(Myself,STATE_CHARMED)~ THEN BEGIN DESIRE_CHARM_CHECK
  SAY ~[DESIRE] Whoa. Sparkly. Pretty colors.~
  = ~[DESIRE] What did you just ask me?~
  IF ~~ THEN EXIT
END

/* begin  morale check */
IF ~HappinessLT(Myself,-290) GlobalLT("c-desireinterest","GLOBAL",5)~ THEN BEGIN BG_MORALE_DROP
  SAY ~[DESIRE] I think I will find my own way out of here. I have had enough of all of this.~
  IF ~~ THEN JOURNAL ~Desire Leaves Forever

  Desire deserted the party today. I always suspected that she did not have the strength to follow me. If our paths cross again, it is likely that she will become hostile.~ GOTO  BG_MORALE_FOREVAR
END

IF ~~ BG_MORALE_FOREVAR
  SAY ~[DESIRE]  Don't bother trying to find me. Have fun being a jackass.~
  IF ~~ THEN DO ~SetGlobal("KickedOut","LOCALS",1) ActionOverride("c-desire",SetLeavePartyDialogFile()) ActionOverride("c-desire",ChangeAIScript("",DEFAULT)) ActionOverride("c-desire",LeaveParty()) ActionOverride("c-desire",EscapeArea())~ EXIT
END

/* First meeting : Prologue */

IF ~AreaCheck("%startingarea%") Global("c-desireentry","GLOBAL",0)~ THEN BEGIN DESIRE_0_PROLOGUE
  SAY ~[DESIRE] You look like you are in a hurry.~
  ++ ~[PC] Ani! When did you get back to Candlekeep!~ DO ~SetGlobal("c-desireentry","GLOBAL",1)~ + INTRO_1
  ++ ~[PC] Desire Anira Laelithar. You return to your humble roots.~ DO ~SetGlobal("c-desireentry","GLOBAL",1)~ + INTRO_2
  ++ ~[PC] The last time I saw you, you were threatening to tear Imoen's eyes out because she took the last piece of cake.~ DO ~SetGlobal("c-desireentry","GLOBAL",1)~ + INTRO_3
  ++ ~[PC] I am in a hurry. Too many chores to do, too many people asking for me... but it is good to see you are back home.~ DO ~SetGlobal("c-desireentry","GLOBAL",1)~ + INTRO_4
  ++ ~[PC] I'm not. I am never in a hurry. I let my servants hurry for me.~ DO ~SetGlobal("c-desireentry","GLOBAL",1)~ + INTRO_5
END

IF ~~ INTRO_1
  SAY ~[DESIRE] Don't call me that. We are not ten summers any more.~
  ++ ~[PC] Still the same old girl. I swear, if I said "don't steal Hulls sword", you would do it just to bug me.~ + INTRO_15
  ++ ~[PC] Fine. Desire Anira Laelithar, I greet you in the manner expected of a lady and a swordswoman.~ + INTRO_35
  ++ ~[PC] No, we are not ten summers any more, or even fourteen. And you most assuredly do not look anything like you did then.~ + INTRO_25
  ++ ~[PC] To me, you will always be the scruffy ruffian who held my face in the trough until Imoen hit you over the head with a broom.~ + INTRO_45
  ++ ~[PC] You look about the same. Talk the same way, too. Still a pain.~ + INTRO_55
END

IF ~~ INTRO_2
  SAY ~[DESIRE] <CHARNAME> I greet you as befits your station in life and your poor choice in companionship.~
  ++ ~[PC] Ooohh! A witty, snarky response instead of a fight! You have changed! Sadly, nothing here has.~ + INTRO_15
  ++ ~[PC] Nice voice, nice speech, nice body... this is not the Ani I knew.~ + INTRO_25
  ++ ~[PC] Alas, my boon companion has been turned from dirty ruffian to sophisticated swordswoman, returning to make my life difficult.~ + INTRO_35
  ++ ~[PC] The last time I saw you, you were throwing various pieces of crockery at my head and saying you never wanted to see me ever again.~ + INTRO_45
  ++ ~[PC] No station, so "<PRO_GIRLBOY>", and no companions, so "lonely". Plus, I have had to do all your chores, so "tired".~ + INTRO_15
END

IF ~~ INTRO_3
  SAY ~[DESIRE] It was my cake. And I was the one going off to apprentice up north, not her.~
  ++ ~[PC] Well, she is still running around talking about it all these years later. You really made her angry.~ + INTRO_15
  ++ ~[PC] The training seems to have agreed with you. You look... different.~ + INTRO_25
  ++ ~[PC] You did not need the cake anyways. If I remember correctly, you stole half of Winthrop's firewine stock and we all got into trouble.~ + INTRO_35
  ++ ~[PC] You always were a self-centered pain in the rear.~ + INTRO_55
  ++ ~[PC] I wish I had gone with you. Or that you had stayed here.~ + INTRO_6
END

IF ~~ INTRO_4
  SAY ~[DESIRE] Is that what this is? I guess you are right. Home. Stinky, dusty, quiet home.~
  ++ ~[PC] Hence yours truly cleaning, dusting, and constantly being told to keep quiet. Gods, I missed you!~ + INTRO_15
  ++ ~[PC] This has been home to both of us for so long. But you have... changed. In appearance, I mean.~ + INTRO_25
  ++ ~[PC] And here you are, all ready to straighten it up and make it more interesting. Or get us all into more trouble.~ + INTRO_35
  ++ ~[PC] Five years away apprenticing, and all you have to say is that? I still have a scar on my left leg you gave me!~ + INTRO_45
  ++ ~[PC] Well, it has been nice talking to you. I had better be going.~ + INTRO_6
END

IF ~~ INTRO_5
  SAY ~[DESIRE] <CHARNAME>. Still the biggest tall-tale-teller of the Sword Coast.~
  ++ ~[PC] There have been big changes around here, you know. They made me Head Reader. And I got married. And rich.~ + INTRO_15
  ++ ~[PC] I know. I am incorrigible. I seem to get away with it more now. But you... you have changed. In appearance, I mean.~ + INTRO_25
  ++ ~[PC] Ah, I have been practicing. Just wait until I start telling everyone 'expanded' versions of what you used to be like as a child.~ + INTRO_35
  ++ ~[PC] I speak only the truth. You should know that by now.~ + INTRO_6
  ++ ~[PC] And you are still an awkward, gawky pain in my rear.~ + INTRO_6
END

IF ~~ INTRO_15
  SAY ~[DESIRE] I may have been away for five summers, but nothing changes in Candlekeep. So why all the rushing about?~
  ++ ~[PC] I have been doing more than my share of chores around here lately.~ + INTRO_6
  ++ ~[PC] I think I have to find Imoen or Gorion or Hull or someone. I keep forgetting what person wants what.~ + INTRO_6
  ++ ~[PC] Actually, I am not rushing. But I do have way too many things to get done.~ + INTRO_6
  ++ ~[PC] The rushing about is a change. We used to have nothing to do but play. Now I have to work and study all day.~ + INTRO_6
  ++ ~[PC] None of your business.~ + INTRO_6
END

IF ~~ INTRO_25
  SAY ~[DESIRE] I know. When I left to study, boys didn't look at me the way they do now. It is a little awkward.~
  ++ ~[PC] Well, there is more to look at now.~ + INTRO_35
  + ~Gender(Player1,MALE)~ + ~[PC] They seem to look at me more now, too. The girls, I mean. Less screaming and running, more smiling and giggling and asking questions. Definitely strange.~ + INTRO_6
  + ~Gender(Player1,FEMALE)~ + ~[PC] They seem to look at me more now, too. Not that I care. Boys are just a distraction.~ + INTRO_6
  ++ ~[PC] Well, you are in luck. Most of our friends have either moved out or moved on. There are only a few of us left here.~ + INTRO_6
  ++ ~[PC] I wish anyone would look at me. But Gorion seems to be everywhere, making sure I am working or studying.~ + INTRO_6
  ++ ~[PC] Hey, Imoen said the same thing the other day. We must be growing up.~ + INTRO_6
END

IF ~~ INTRO_35
  SAY ~[DESIRE] You know I can still sneak cow dung into your bed, right?~
  ++ ~[PC] So they couldn't shape you up into a true and loyal follower of Helm. I knew it!~ + INTRO_6
  ++ ~[PC] Your deep dark secrets are safe with me. For a suitable price, of course.~ + INTRO_6
  ++ ~[PC] Some things never change.~ + INTRO_6
  ++ ~[PC] Hey! You have an advantage! You know where I sleep, and you will probably have to bunk in the guardhouse! No fair!~ + INTRO_6
  ++ ~[PC] Hey, Imoen said the same thing the other day. Great... now I have to deal with two of you.~ + INTRO_6
END

IF ~~ INTRO_45
  SAY ~[DESIRE] You deserved it. You pinched me, remember?~
  ++ ~[PC] I am glad you are back. I have been doing more than my share of chores around here lately.~ + INTRO_6
  ++ ~[PC] Some things never change.~ + INTRO_6
  ++ ~[PC] Are you staying in the guard barracks? Oh... wait... chores. I had better go.~ + INTRO_6
  ++ ~[PC] Hey, Imoen said the same thing the other day. Great... now I have to deal with two of you.~ + INTRO_6
  ++ ~[PC] Sure. You always did have a strange way of evaluating "appropriate response".~ + INTRO_6
END

IF ~~ INTRO_55
  SAY ~[DESIRE] The feeling is mutual. Still a stuck-up...~
  = ~[DESIRE] Wait. I didn't mean that. It's just... well, it is hard to break old habits, I guesss.~
  ++ ~[PC] Me either. You have changed. I am not sure I have changed. I wish I had gone away to apprentice, and you had stayed here.~ + INTRO_6
  ++ ~[PC] I am glad you are back. I have been doing more than my share of chores around here lately.~ + INTRO_6
  ++ ~[PC] Some things never change.~ + INTRO_6
  ++ ~[PC] If that was an apology, I accept.~ + INTRO_6
  ++ ~[PC] Old habits are good habits. We are not likely to ever settle our differences, are we?~ + INTRO_6
END

IF ~~ INTRO_6
  SAY ~[DESIRE] You seem to be in a rush. I'm not going anywhere. Imoen was looking for you. Come back and talk later. If you want to.~
  = ~[DESIRE] I mean, if you have the time. Or if you don't want to, that's ok.~
  ++ ~[PC] Of course I want to. Look, wait here for awhile, and we can catch up.~ + PRO_WAIT_HERE
  ++ ~[PC] That talk may have to wait for awhile. I suspect I have a few rounds of chores to do. Perhaps I will see you tomorrow.~ + PRO_GO_ON
  ++ ~[PC] I think that is the longest sentence I have ever heard you say. Are you feeling well?~ + PRO_GO_ON
  ++ ~[PC] I guess things have changed a little. Ordinarily, you would have slapped me and demanded that we talk right now.~ + PRO_GO_ON
  ++ ~[PC] I will be back in a few minutes. You wait right here.~ + PRO_WAIT_HERE
END

IF ~AreaCheck("%startingarea%") Global("c-desireentry","GLOBAL",1)~ THEN BEGIN DESIRE_1_PROLOGUE
	SAY ~[DESIRE] You are back again. Did you find you had some time to talk?~
	++ ~[PC] No. I just wanted to say it was good to see you again. I might be back in a minute or two.~ + PRO_WAIT_HERE
	++ ~[PC] No. I just wanted to say it was good to see you again. I will talk to you tommorow.~ + PRO_GO_ON
	++ ~[PC] Do you want to join me and help with the chores?~ + PRO_HELP_CHORES
	++ ~[PC] Heya. It's me, <CHARNAME>. Time to test if a script using MakeGlobal() and MoveToArea() works in the new engine...~ + PRO_GO_ON
END

IF ~!AreaCheck("%startingarea%") Global("c-desirechapter1","GLOBAL",0)~ THEN BEGIN DESIRE_0_CHAPTERONE
	SAY ~[DESIRE] Hello there. This is the chapter 1 join-up talk. This is where we expand our backstory.~
	++ ~[PC] OK. Join up.~ + CH1_GO_ON
	++ ~[PC] Wait here.~ + CH1_WAIT
END

IF ~!AreaCheck("%startingarea%") Global("c-desirechapter1","GLOBAL",1)~ THEN BEGIN DESIRE_1_CHAPTERONE
	SAY ~[DESIRE] You are back again. We already had the joining talk.~
	++ ~[PC] OK. Join up.~ + CH1_GO_ON
	++ ~[PC] Wait here.~ + CH1_WAIT
END

IF ~~ PRO_HELP_CHORES
  SAY ~[DESIRE] I... no. I have to unpack. And I have to get some other things done.~
  IF ~~ THEN GOTO PRO_GO_ON
END

IF ~~ PRO_WAIT_HERE
  SAY ~[DESIRE] Well, it has been nice talking to you. Gods, that sounded all formal and everything.~
  IF ~~ THEN DO ~SetGlobal("c-desireentry","GLOBAL",1)~ EXIT
END

IF ~~ PRO_GO_ON
  SAY ~[DESIRE] I don't know. See you tomorrow. You look... ok. See you tomorrow.~
  IF ~~ THEN DO ~SetGlobal("c-desiremoves","GLOBAL",1)~ EXIT
END

IF ~~ CH1_GO_ON
  SAY ~[DESIRE] Ok. I have nothing better to do anyways.~
  IF ~~ THEN DO ~SetGlobal("KickedOut","LOCALS",0) JoinParty()~ EXIT
END

IF ~~ CH1_WAIT
  SAY ~[DESIRE] Fine. I will wait here. But I am better prepared that you are. You should let me come along.~
  IF ~~ THEN EXIT
END


END // of append to C-DESIRE

APPEND ~C-DESIRP~

IF ~StateCheck(Myself,STATE_CHARMED)~ THEN BEGIN DESIRE_CHARM_CHECK
  SAY ~[DESIRE] Whoa. Sparkly. Pretty colors.~
  = ~[DESIRE] What did you just ask me? Hey, where did I put that potion...~
  IF ~~ THEN EXIT
END

/* begin  morale check */
IF ~HappinessLT(Myself,-290) GlobalLT("c-desireinterest","GLOBAL",5)~ THEN BEGIN BG_MORALE_DROP
  SAY ~[DESIRE] I think I will find my own way out of here. I have had enough of all of this.~
  IF ~~ THEN JOURNAL ~Desire Leaves Forever

  Desire deserted the party today. I always suspected that she did not have the strength to follow me. If our paths cross again, it is likely that she will become hostile.~ GOTO  BG_MORALE_FOREVAR
END

IF ~~ BG_MORALE_FOREVAR
  SAY ~[DESIRE]  Don't bother trying to find me. Have fun being a jackass.~
  IF ~~ THEN DO ~SetGlobal("KickedOut","LOCALS",1) ActionOverride("c-desire",SetLeavePartyDialogFile()) ActionOverride("c-desire",ChangeAIScript("",DEFAULT)) ActionOverride("c-desire",LeaveParty()) ActionOverride("c-desire",EscapeArea())~ EXIT
END

IF ~HappinessLT(Myself,-290) GlobalGT("c-desireinterest","GLOBAL",4)~ THEN BEGIN BG_MORALE_INTEREST
  SAY ~[DESIRE] I have had enough of all of this. The only thing keeping me around is... well, you are interesting.~
  ++ ~[PC] Sorry, but I do not want you back in the group just yet.~ + NOJOIN_WAIT
  ++ ~[PC] I could use you. Join me.~ + JOIN_AFRAID_OF
END

IF ~!HappinessLT(Myself,-290) Global("KickedOut","LOCALS",1)~ THEN BEGIN DESIRE_REJOIN
  SAY ~[DESIRE] I could come along. If you want me to. Or not.~
  ++ ~[PC] Sorry, but I do not want you back in the group just yet.~ + NOJOIN_WAIT
  ++ ~[PC] I could use you. Join me.~ + JOIN_AFRAID_OF
END

IF ~~ JOIN_AFRAID_OF
  SAY ~[DESIRE] Poor choice of words. At least, I hope it is. But I will follow you.~
  IF ~~ THEN DO ~SetGlobal("KickedOut","LOCALS",0) JoinParty() ~ EXIT
END

IF ~~ NOJOIN_WAIT
  SAY ~[DESIRE] I will be here. I think.~
  IF ~~ THEN DO ~SetGlobal("KickedOut","LOCALS",1)~ EXIT
END

END // of append to C-DESIRP


// APPEND ~C-DESIRB~ END // of append to C-DESIRB

APPEND ~C-DESIRJ~

IF ~StateCheck(Myself,STATE_CHARMED)~ THEN BEGIN DESIRE_CHARM_CHECK
  SAY ~[DESIRE] Whoa. Sparkly. Pretty colors.~
  = ~[DESIRE] What did you just ask me?~
  IF ~~ THEN EXIT
END

/* begin  morale check */
IF ~HappinessLT(Myself,-290) GlobalLT("c-desireinterest","GLOBAL",5)~ THEN BEGIN BG_MORALE_DROP
  SAY ~[DESIRE] I think I will find my own way out of here. I have had enough of all of this.~
  IF ~~ THEN JOURNAL ~Desire Leaves Forever

  Desire deserted the party today. I always suspected that she did not have the strength to follow me. If our paths cross again, it is likely that she will become hostile.~ GOTO  BG_MORALE_FOREVAR
END

IF ~~ BG_MORALE_FOREVAR
  SAY ~[DESIRE]  Don't bother trying to find me. Have fun being a jackass.~
  IF ~~ THEN DO ~SetGlobal("KickedOut","LOCALS",1) ActionOverride("c-desire",SetLeavePartyDialogFile()) ActionOverride("c-desire",ChangeAIScript("",DEFAULT)) ActionOverride("c-desire",LeaveParty()) ActionOverride("c-desire",EscapeArea())~ EXIT
END
/* end of morale check */

/* Friend Talks */
/* Friend Talk 1 : */
IF ~Global("c-desirefriendbg","GLOBAL",1)~ THEN BEGIN BG_FT_1
  SAY ~[DESIRE] We seem to be attracting death and destruction. Lots of it. BG_FT_1 ~
  ++ ~[PC] reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",2) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",2) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",2) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",2) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",2) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 2 : */
IF ~Global("c-desirefriendbg","GLOBAL",3)~ THEN BEGIN BG_FT_2
  SAY ~[DESIRE] Do you ever get the feeling we were really not prepared for all this? BG_FT_2 ~
  ++ ~[PC] reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",4) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",4) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",4) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",4) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",4) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 3 : */
IF ~Global("c-desirefriendbg","GLOBAL",5)~ THEN BEGIN BG_FT_3
  SAY ~[DESIRE] I don't know which is better... a sharp edged blade, a fast casting spell, or the ability to blend into the shadows. BG_FT_3 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",6) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",6) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",6) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",6) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",6) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 4 : */
IF ~Global("c-desirefriendbg","GLOBAL",7)~ THEN BEGIN BG_FT_4
  SAY ~[DESIRE] Did you ever get a chance to talk to Miraane before you left? BG_FT_4 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",8) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",8) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",8) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",8) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",8) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 5 : */
IF ~Global("c-desirefriendbg","GLOBAL",9)~ THEN BEGIN BG_FT_5
  SAY ~[DESIRE] I wish I had a goal. Or a direction. Or maybe not. BG_FT_5 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",10) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",10) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",10) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",10) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",10) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 6 : */
IF ~Global("c-desirefriendbg","GLOBAL",11)~ THEN BEGIN BG_FT_6
  SAY ~[DESIRE] Why do our opponents always talk before they attack? BG_FT_6 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",12) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",12) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",12) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",12) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",12) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 7 : */
IF ~Global("c-desirefriendbg","GLOBAL",13)~ THEN BEGIN BG_FT_7
  SAY ~[DESIRE] Do you think... do you think I am useful? BG_FT_7 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",14) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",14) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",14) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",14) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",14) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 8 : */
IF ~Global("c-desirefriendbg","GLOBAL",15)~ THEN BEGIN BG_FT_8
  SAY ~[DESIRE] I can't believe we did that. I mean, I can, but I don't know why we did that. BG_FT_8 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",16) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",16) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",16) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",16) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",16) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 9 : */
IF ~Global("c-desirefriendbg","GLOBAL",17)~ THEN BEGIN BG_FT_9
  SAY ~[DESIRE] BG_FT_9 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",18) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",18) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",18) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",18) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",18) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 10 : */
IF ~Global("c-desirefriendbg","GLOBAL",19)~ THEN BEGIN BG_FT_10
  SAY ~[DESIRE] BG_FT_10 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",20) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",20) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",20) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",20) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",20) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 11 : */
IF ~Global("c-desirefriendbg","GLOBAL",21)~ THEN BEGIN BG_FT_11
  SAY ~[DESIRE] BG_FT_11 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",22) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",22) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",22) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",22) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",22) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 12 : */
IF ~Global("c-desirefriendbg","GLOBAL",23)~ THEN BEGIN BG_FT_12
  SAY ~[DESIRE] BG_FT_12 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",24) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",24) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",24) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",24) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",24) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 13 : */
IF ~Global("c-desirefriendbg","GLOBAL",25)~ THEN BEGIN BG_FT_13
  SAY ~[DESIRE] BG_FT_13 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",26) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",26) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",26) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",26) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",26) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 14 : */
IF ~Global("c-desirefriendbg","GLOBAL",27)~ THEN BEGIN BG_FT_14
  SAY ~[DESIRE] BG_FT_14 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",28) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",28) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",28) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",28) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",28) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* Friend Talk 15 : */
IF ~Global("c-desirefriendbg","GLOBAL",29)~ THEN BEGIN BG_FT_15
  SAY ~[DESIRE] BG_FT_15 ~
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",30) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_01
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",30) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_02
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",30) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_03
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",30) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_04
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirefriendbg","GLOBAL",30) RealSetGlobalTimer("c-desirefriendtimer","GLOBAL",%DESIRE_FTT%)~ + TALK_05
END
/* end of triggered states - GOTO Friend Talk Responses */
/* Romance Talks */
/* Romance Talk 1 : */
IF ~Global("c-desirerombg","GLOBAL",1)~ THEN BEGIN BG_LT_1
  SAY ~[DESIRE] BG_LT_1 ~
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",2) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",0) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",2) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",2) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",2) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 2 : */
IF ~Global("c-desirerombg","GLOBAL",3)~ THEN BEGIN BG_LT_2
  SAY ~[DESIRE] BG_LT_2 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",4) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",4) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",4) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",4) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",4) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 3 : */
IF ~Global("c-desirerombg","GLOBAL",5)~ THEN BEGIN BG_LT_3
  SAY ~[DESIRE] BG_LT_3 ~
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",6) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",6) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",6) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",6) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",6) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 4 : */
IF ~Global("c-desirerombg","GLOBAL",7)~ THEN BEGIN BG_LT_4
  SAY ~[DESIRE] BG_LT_4 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",8) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",8) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",8) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",8) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",8) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 5 : */
IF ~Global("c-desirerombg","GLOBAL",9)~ THEN BEGIN BG_LT_5
  SAY ~[DESIRE] BG_LT_5 ~
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",10) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",10) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",10) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",10) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC]  reply_temp ~ DO ~SetGlobal("c-desirerombg","GLOBAL",10) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 6 : */
IF ~Global("c-desirerombg","GLOBAL",11)~ THEN BEGIN BG_LT_6
  SAY ~[DESIRE] BG_LT_6 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",12) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",12) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",12) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",12) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",12) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 7 : */
IF ~Global("c-desirerombg","GLOBAL",13)~ THEN BEGIN BG_LT_7
  SAY ~[DESIRE] BG_LT_7 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",14) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",14) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",14) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",14) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",14) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 8 : */
IF ~Global("c-desirerombg","GLOBAL",15)~ THEN BEGIN BG_LT_8
  SAY ~[DESIRE] BG_LT_8 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",16) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",16) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",16) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",16) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",16) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 9 : */
IF ~Global("c-desirerombg","GLOBAL",17)~ THEN BEGIN BG_LT_9
  SAY ~[DESIRE] BG_LT_9 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",18) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",18) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",18) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",18) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",18) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 10 : */
IF ~Global("c-desirerombg","GLOBAL",19)~ THEN BEGIN BG_LT_10
  SAY ~[DESIRE] BG_LT_10 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",20) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",20) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",20) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",20) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",20) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 11 : */
IF ~Global("c-desirerombg","GLOBAL",21)~ THEN BEGIN BG_LT_11
  SAY ~[DESIRE] BG_LT_11 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",22) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",22) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",22) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",22) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",22) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 12 : */
IF ~Global("c-desirerombg","GLOBAL",23)~ THEN BEGIN BG_LT_12
  SAY ~[DESIRE] BG_LT_12 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",24) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",24) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",24) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",24) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",24) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 13 : */
IF ~Global("c-desirerombg","GLOBAL",25)~ THEN BEGIN BG_LT_13
  SAY ~[DESIRE] BG_LT_13 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",26) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",26) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",26) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",26) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",26) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 14 : */
IF ~Global("c-desirerombg","GLOBAL",27)~ THEN BEGIN BG_LT_14
  SAY ~[DESIRE] BG_LT_14 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",28) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",28) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",28) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",28) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",28) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* Romance Talk 15 : */
IF ~Global("c-desirerombg","GLOBAL",29)~ THEN BEGIN BG_LT_15
  SAY ~[DESIRE] BG_LT_15 ~
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",30) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_01
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",30) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_02
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",30) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_03
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",30) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_04
  ++ ~[PC] reply_temp  ~ DO ~SetGlobal("c-desirerombg","GLOBAL",30) RealSetGlobalTimer("c-desireromtimer","GLOBAL",%DESIRE_LTT%)~ + ROM_05
END
/* end of triggered states - GOTO Romance Talk Responses */
/* Friend Talk Responses */
IF ~~ TALK_01 SAY ~[DESIRE] Well, this ends reply state TALK_01.~ IF ~~ THEN EXIT END
IF ~~ TALK_02 SAY ~[DESIRE] Well, this ends reply state TALK_02.~ IF ~~ THEN EXIT END
IF ~~ TALK_03 SAY ~[DESIRE] Well, this ends reply state TALK_03.~ IF ~~ THEN EXIT END
IF ~~ TALK_04 SAY ~[DESIRE] Well, this ends reply state TALK_04.~ IF ~~ THEN EXIT END
IF ~~ TALK_05 SAY ~[DESIRE] Well, this ends reply state TALK_05.~ IF ~~ THEN EXIT END
/* end of Friend Talk Responses */

/* Romance Talk Responses */
IF ~~ ROM_01  SAY ~[DESIRE] Well, this ends reply state ROM_01.~ IF ~~ THEN EXIT END
IF ~~ ROM_02  SAY ~[DESIRE] Well, this ends reply state ROM_02.~ IF ~~ THEN EXIT END
IF ~~ ROM_03  SAY ~[DESIRE] Well, this ends reply state ROM_03.~ IF ~~ THEN EXIT END
IF ~~ ROM_04  SAY ~[DESIRE] Well, this ends reply state ROM_04.~ IF ~~ THEN EXIT END
IF ~~ ROM_05  SAY ~[DESIRE] Well, this ends reply state ROM_05.~ IF ~~ THEN EXIT END
/* end of Romance Talk Responses */

/* NPC Initiated Flirts */
IF ~Global("c-desirelightflirt","GLOBAL",1)~ THEN BEGIN BG_NPC_FLIRT
  SAY ~[DESIRE] flirt_state_start ~
  /* NPC Initiated Flirts : Light Flirts */
  IF ~RandomNum(16,1)~ THEN GOTO BG_NPC_FLIRT_1
  IF ~RandomNum(16,2)~ THEN GOTO BG_NPC_FLIRT_2
  IF ~RandomNum(16,3)~ THEN GOTO BG_NPC_FLIRT_3
  IF ~RandomNum(16,4)~ THEN GOTO BG_NPC_FLIRT_4
  IF ~RandomNum(16,5)~ THEN GOTO BG_NPC_FLIRT_5
  IF ~RandomNum(16,6)~ THEN GOTO BG_NPC_FLIRT_6
  IF ~RandomNum(16,7)~ THEN GOTO BG_NPC_FLIRT_7
  IF ~RandomNum(16,8)~ THEN GOTO BG_NPC_FLIRT_8
  IF ~RandomNum(16,9)~ THEN GOTO BG_NPC_FLIRT_9
  IF ~RandomNum(16,10)~ THEN GOTO BG_NPC_FLIRT_10
  IF ~RandomNum(16,11)~ THEN GOTO BG_NPC_FLIRT_11
  IF ~RandomNum(16,12)~ THEN GOTO BG_NPC_FLIRT_12
  IF ~RandomNum(16,13)~ THEN GOTO BG_NPC_FLIRT_13
  IF ~RandomNum(16,14)~ THEN GOTO BG_NPC_FLIRT_14
  IF ~RandomNum(16,15)~ THEN GOTO BG_NPC_FLIRT_15
  IF ~RandomNum(16,16)~ THEN GOTO BG_NPC_FLIRT_16
END
IF ~~ BG_NPC_FLIRT_1
  SAY ~[DESIRE] BG_NPC_FLIRT_1 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_2
  SAY ~[DESIRE] BG_NPC_FLIRT_2 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_3
  SAY ~[DESIRE] BG_NPC_FLIRT_3 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_4
  SAY ~[DESIRE] BG_NPC_FLIRT_4 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_5
  SAY ~[DESIRE] BG_NPC_FLIRT_5 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_6
  SAY ~[DESIRE] BG_NPC_FLIRT_6 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_7
  SAY ~[DESIRE] BG_NPC_FLIRT_7 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_8
  SAY ~[DESIRE] BG_NPC_FLIRT_8 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_9
  SAY ~[DESIRE] BG_NPC_FLIRT_9 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_10
  SAY ~[DESIRE] BG_NPC_FLIRT_10 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_11
  SAY ~[DESIRE] BG_NPC_FLIRT_11 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_12
  SAY ~[DESIRE] BG_NPC_FLIRT_12 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_13
  SAY ~[DESIRE] BG_NPC_FLIRT_13 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_14
  SAY ~[DESIRE] BG_NPC_FLIRT_14 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_15
  SAY ~[DESIRE] BG_NPC_FLIRT_15 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
IF ~~ BG_NPC_FLIRT_16
  SAY ~[DESIRE] BG_NPC_FLIRT_16 ~
  IF ~~ THEN DO ~IncrementGlobal("c-desireinterest","GLOBAL",1) SetGlobal("c-desirelightflirt","GLOBAL",0) RealSetGlobalTimer("c-desireflirttimer","GLOBAL",%DESIRE_FLIRT%)~ EXIT
END
/* end of npc-initiated flirts */

/* PC Initiated Flirts from PID */
IF ~~ PID_FLIRT_PC
  SAY ~[DESIRE] So are you.~
  /* NPC Initiated Flirts : Light Flirts for BG content */
  /* ACTION */
  IF ~RandomNum(4,1)~ THEN GOTO BG_PC_FLIRT_1
  IF ~RandomNum(4,2)~ THEN GOTO BG_PC_FLIRT_2
  IF ~RandomNum(4,3)~ THEN GOTO BG_PC_FLIRT_3
  IF ~RandomNum(4,4)~ THEN GOTO BG_PC_FLIRT_4
  /* COMPLIMENT */
  IF ~RandomNum(4,1)~ THEN GOTO BG_PC_FLIRT_5
  IF ~RandomNum(4,2)~ THEN GOTO BG_PC_FLIRT_6
  IF ~RandomNum(4,3)~ THEN GOTO BG_PC_FLIRT_7
  IF ~RandomNum(4,4)~ THEN GOTO BG_PC_FLIRT_8
  /* NONVERBAL */
  IF ~RandomNum(4,1)~ THEN GOTO BG_PC_FLIRT_9
  IF ~RandomNum(4,2)~ THEN GOTO BG_PC_FLIRT_10
  IF ~RandomNum(4,3)~ THEN GOTO BG_PC_FLIRT_11
  IF ~RandomNum(4,4)~ THEN GOTO BG_PC_FLIRT_12
  /* EVIL */
  IF ~RandomNum(4,1)~ THEN GOTO BG_PC_FLIRT_13
  IF ~RandomNum(4,2)~ THEN GOTO BG_PC_FLIRT_14
  IF ~RandomNum(4,3)~ THEN GOTO BG_PC_FLIRT_15
  IF ~RandomNum(4,4)~ THEN GOTO BG_PC_FLIRT_16
END

/* ACTION */
IF ~~ BG_PC_FLIRT_1 SAY ~[DESIRE] BG_PC_FLIRT_1 ~ IF ~~ THEN EXIT END
IF ~~ BG_PC_FLIRT_2 SAY ~[DESIRE] BG_PC_FLIRT_2 ~ IF ~~ THEN EXIT END
IF ~~ BG_PC_FLIRT_3 SAY ~[DESIRE] BG_PC_FLIRT_3 ~ IF ~~ THEN EXIT END
IF ~~ BG_PC_FLIRT_4 SAY ~[DESIRE] BG_PC_FLIRT_4 ~ IF ~~ THEN EXIT END
/* COMPLIMENT */
IF ~~ BG_PC_FLIRT_5 SAY ~[DESIRE] BG_PC_FLIRT_5 ~ IF ~~ THEN EXIT END
IF ~~ BG_PC_FLIRT_6 SAY ~[DESIRE] BG_PC_FLIRT_6 ~ IF ~~ THEN EXIT END
IF ~~ BG_PC_FLIRT_7 SAY ~[DESIRE] BG_PC_FLIRT_7 ~ IF ~~ THEN EXIT END
IF ~~ BG_PC_FLIRT_8 SAY ~[DESIRE] BG_PC_FLIRT_8 ~ IF ~~ THEN EXIT END
/* NONVERBAL */
IF ~~ BG_PC_FLIRT_9 SAY ~[DESIRE] BG_PC_FLIRT_9 ~ IF ~~ THEN EXIT END
IF ~~ BG_PC_FLIRT_10 SAY ~[DESIRE] BG_PC_FLIRT_10 ~ IF ~~ THEN EXIT END
IF ~~ BG_PC_FLIRT_11 SAY ~[DESIRE] BG_PC_FLIRT_11 ~ IF ~~ THEN EXIT END
IF ~~ BG_PC_FLIRT_12 SAY ~[DESIRE] BG_PC_FLIRT_12 ~ IF ~~ THEN EXIT END
/* EVIL */
IF ~~ BG_PC_FLIRT_13 SAY ~[DESIRE] BG_PC_FLIRT_13 ~ IF ~~ THEN EXIT END
IF ~~ BG_PC_FLIRT_14 SAY ~[DESIRE] BG_PC_FLIRT_14 ~ IF ~~ THEN EXIT END
IF ~~ BG_PC_FLIRT_15 SAY ~[DESIRE] BG_PC_FLIRT_15 ~ IF ~~ THEN EXIT END
IF ~~ BG_PC_FLIRT_16 SAY ~[DESIRE] BG_PC_FLIRT_16 ~ IF ~~ THEN EXIT END

/* end of PC flirting with Desire flirts */

/* PID - Always add last */

/* PID : Gabber not PC */
IF ~!IsGabber(Player1) !IsGabber("c-desire")~ THEN PID_OTHER SAY ~[DESIRE] Look, <GABBER>, I'm busy right now. If <CHARNAME> wants to ask me something, <PRO_HESHE> can. Now leave me alone.~ IF ~~ THEN EXIT END
IF ~!IsGabber(Player1) IsGabber("c-desire")~ THEN PID_SELFAWARE
  SAY ~[DESIRE] Great. Now I am talking to myself.~
  IF ~!InParty("edwin")~ THEN EXIT
  IF ~InParty("edwin")~ THEN GOTO PID_SELFAWARE_EDWIN
END
IF ~~ PID_SELFAWARE_EDWIN SAY ~[DESIRE] Next thing you know, I will be muttering to myself like Edwin. I  had better find a distraction.~ IF ~~ THEN EXIT END
/* PID : Gabber is PC */
IF ~IsGabber(Player1)~ THEN PID_PC
  SAY ~[DESIRE] What do you want?~
  ++ ~[PC] I want to ask you something.~ + PID_ASK_PC
  ++ ~[PC] I think your voice is very strange right now... perhaps you should clear your throat.~ + PID_STRINGFIX_PC
  ++ ~[PC] Talk to me.~ + PID_TALK_PC
  + ~Gender(Player1,MALE) !HasItemEquiped("belt05",Player1)~ + ~[PC] I think you are very... interesting. (men) ~ + PID_FLIRT_PC
  + ~Gender(Player1,FEMALE) !HasItemEquiped("belt05",Player1)~ + ~[PC] I think you are very... interesting. (women) ~ + PID_NOFLIRT_PC
  + ~HasItemEquiped("belt05",Player1)~ + ~[PC] I think you are very... interesting. (belt) ~ + PID_GIRDLE_PC
  ++ ~[PC] Actually, I really have nothing to talk about right now.~ + PID_FINISH_PC
END
IF ~~ PID_ASK_PC SAY ~[DESIRE] I suppose I might answer. Or not.~ IF ~~ THEN EXIT END
IF ~~ PID_STRINGFIX_PC SAY ~[DESIRE] *cough* ~ IF ~~ THEN EXIT END
IF ~~ PID_TALK_PC SAY ~[DESIRE] You are lonely enough that you want me to entertain you. Fine...~ IF ~~ THEN EXIT END
IF ~~ PID_FINISH_PC SAY ~[DESIRE] Me either. So let's not talk.~ IF ~~ THEN EXIT END
IF ~~ PID_NOFLIRT_PC SAY ~[DESIRE] So are you. In a completely non-romantic, platonic kind of way, that is.~ IF ~~ THEN EXIT END
IF ~~ PID_GIRDLE_PC SAY ~[DESIRE] Not half as interesting as I will be if you don't take that thing off. It kind of bothers me to have you shifting from male to female, female to male.~ IF ~~ THEN EXIT END

END // of append to c-desirj
