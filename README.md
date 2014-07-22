{
	"name": "AOT",
	"altname": "Attack on Titan",
	"author": ["Windblown"],
	"threadlink": "http://pokemon-online.eu/forums/showthread.php?24865-Attack-on-Titan",
	"summary": "Seid ihr das Essen? Nein, wir sind der Jäger! Humanity is under attack by the Titans who have broken through their walls. Lead the defense of humanity under an elite group of fighters, including Eren, Mikasa, Armin, and Levi. TESTING: Mike (counters all night actions g_g)",
	"sides": [
		{
			"side": "village",
			"translation": "104th Training Corps",
			"winmsg": "Humanity is free of the Titans and can now venture into the world beyond the walls! Good work, ~Players~!"
		},
		{
			"side": "titan",
			"translation": "Titans",
			"winmsg": "The Titans, ~Players~, have devoured every last human on Earth!"
		},
		{	
			"side": "titan2",
			"translation": "Titan Shifters",
			"winmsg": "Not satisfied with exterminating all humans, the Titan Shifters, ~Players~, have proven themselves the dominant Titans."
		},
		{
			"side": "titan3",
			"translation": "Wall Titan",
			"winmsg": "Somehow, ~Players~, stuck in the wall, has won by themselves!"
		}
	],
	"ticks": {
		"night": 40,
		"night1": 40
	},
	"roles": [
		{
			"role": "recruit",
			"translation": "Recruit",
			"side": "village",
			"help": "A budding soldier hoping to participate in the war against the Titans. You aren't quite skilled enough to go into combat, but you can vote during the day!",
			"actions": {
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "keith",
			"translation": "Keith",
			"side": "village",
			"help": "The instructor of the 104th Training Corps, you're responsible for choosing who will attack the Titans! Type /muster during the night to convert the first division (Mikasa, Armin, Krista, and Ymir), or /muster2 to convert the second division (Jean, Marco, Connie, and Sasha)! You cannot do both commands in the same night. You can also /expose every other day to reveal someone's role. You won't be revealed in the process.",
			"info": "Can muster the first division (Mikasa, Armin, Krista, Ymir) or the second division (Jean, Marco, Connie, Sasha) during the night. Can /expose one person every other day in bigger games (14+). Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"muster": {
						"command": "massconvert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 100,
						"restrict": ["muster2"],
						"convertRoles": {
							"mikasa": "mikasa2",
							"armin": "armin2",
							"ymir": "ymir2",
							"krista": "krista2"
						},
					"singlemassconvertmsg": "Keith has summoned the first division to move out! (THE PEOPLE WITH 3-D AFTER THEIR NAMES SHARE A NIGHTKILL.)"
					},
					"muster2": {
						"command": "massconvert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 100,
						"hide": true,
						"restrict": ["muster"],
						"convertRoles": {
							"jean": "jean2",
							"connie": "connie2",
							"marco": "marco2",
							"sasha": "sasha2"
						},
					"singlemassconvertmsg": "Keith has summoned the second division to move out! (THE PEOPLE WITH 3-D AFTER THEIR NAMES SHARE A NIGHTKILL.)"
					}
				},
				"standby": {
					"expose": {
						"target": "AnyButSelf",
						"recharge": 2,
						"msg": "You can expose someone with /expose! You won't be revealed!",
						"exposemsg": "Keith sized up the soldiers standing in front of him when he stopped in front of ~Target~. 'SOLDIER, WHAT IS YOUR NAME AND WHY ARE YOU HERE?' 'I AM THE ~Role~ AND I'M HERE TO FIGHT THE TITANS!' ~Target~ managed to answer."
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "keiths",
			"translation": "Keith",
			"side": "village",
			"help": "The instructor of the 104th Training Corps, you're responsible for choosing who will attack the Titans! Type /muster during the night to convert the first division (Mikasa, Armin, Krista, and Ymir), or /muster2 to convert the second division (Jean, Marco, Connie, and Sasha)! You cannot do both commands in the same night.",
			"info": "Can muster the first division (Mikasa, Armin, Krista, Ymir) or the second division (Jean, Marco, Connie, Sasha) during the night. Sided with 104th Training Corps.",
			"hide": true,
			"actions": {
				"night": {
					"muster": {
						"command": "massconvert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 100,
						"hide": true,
						"restrict": ["muster2"],
						"convertRoles": {
							"mikasa": "mikasa2",
							"armin": "armin2",
							"ymir": "ymir2",
							"krista": "krista2"
						},
					"singlemassconvertmsg": "Keith has summoned the first division to move out! (THE PEOPLE WITH 3-D AFTER THEIR NAMES SHARE A NIGHTKILL.)"
					},
					"muster2": {
						"command": "massconvert",
						"target": "OnlySelf",
						"common": "Self",
						"priority": 100,
						"hide": true,
						"restrict": ["muster"],
						"convertRoles": {
							"jean": "jean2",
							"connie": "connie2",
							"marco": "marco2",
							"sasha": "sasha2"
						},
					"singlemassconvertmsg": "Keith has summoned the second division to move out! (THE PEOPLE WITH 3-D AFTER THEIR NAMES SHARE A NIGHTKILL.)"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "eren",
			"translation": "Eren",
			"side": "village",
			"help": "You're going to kill all the Titans...yet you are a Titan Shifter yourself! Type /convert on yourself to don your 3-D manuever gear, but be careful - you may turn into a Titan instead!",
			"info": "Can convert, either equipping 3-D manuever gear(70%) or Titan form (30%). Inspects as a Titan to Zoe. Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"convert": {
						"target": "OnlySelf",
						"common": "Self",
						"priority": 90,
						"convertmsg": "Eren's rage is motivating him to kill all Titans...he has transformed!",
						"newRole": {
							"random": {
								"eren2": 0.7,
								"erent": 0.3
							}
						}
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is a Titan!"
				}
			}
		},
		{
			"role": "eren2",
			"translation": "Eren (Flight)",
			"side": "village",
			"help": "Take flight! You've put on your 3-D Manuever Gear, so you can now /kill every night! You will convert back the following night, so make your kill count!",
			"info": "Can kill one person during the night. Converts back after one night. Inspects as a Titan to Zoe. Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"kill": {
						"target": "AnyButSelf",
						"common": "Self",
						"priority": 20,
						"msg": "'I'LL KILL EVERY LAST ONE OF THEM!' Eren shouted in his rage. You were no exception."
					}
				},
				"initialCondition": {
					"curse": {
						"curseCount": 2,
						"cursedRole": "eren"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is a Titan!"
				}
			}
		},
		{
			"role": "erent",
			"translation": "Eren (Titan)",
			"side": "village",
			"help": "You've accidentally turned into a Titan! While you're still helping humanity, your strength is uncontrollable at times. You can /punch during the night to kill someone, but you have a chance (25%) of killing yourself instead. Fortunately, you have a 50% chance of evading nightkills!",
			"info": "Can kill one person during the night with a suicide chance of 25%. Evades 50% of nightkills. Inspects as a Titan to Zoe. Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"punch": {
						"command": "kill",
						"target": "AnyButSelf",
						"common": "Self",
						"priority": 20,
						"suicideChance": 0.25,
						"msg": "It's strange...it's as almost as if the Titan looming over you looks just like Eren. How about that for some last thoughts?"
					}
				},
				"kill": {
					"mode": {
						"evadeChance": 0.5
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is a Titan!"
				}
			}
		},
		{
			"role": "firstdivision",
			"translation": "First and Second Divisions",
			"side": "village",
			"hide": true,
			"help": "nope",
			"info": "nope",
			"actions": {
				"night": {
					"kill": {
						"target": "AnyButSelf",
						"common": "Team",
						"priority": 18
					}
				}
			}
		},
		{
			"role": "mikasa",
			"translation": "Mikasa",
			"side": "village",
			"help": "The adopted sister of Eren, you have sworn to protect him, as he is the only family you have left. Type /protect to protect someone during the night! You are part of the First Division, and will convert if Keith assembles it.",
			"info": "Can protect one person during the night. Part of the First Division. Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"protect": {
						"target": "AnyButSelf",
						"common": "Self",
						"priority": 10
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "mikasa2",
			"translation": "Mikasa (3-D)",
			"side": "village",
			"help": "First Division, move out! You can still /protect during the night, but you also share a /kill with the rest of the First Division (Armin, Ymir, and Krista)! You will convert back in one night, so use your kill wisely!",
			"info": "Can protect one person during the night. Can kill one person during the night (shared with First Division). Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"protect": {
						"target": "AnyButSelf",
						"common": "Self",
						"priority": 10,
						"hide": true
					},
					"kill": {
						"target": "AnyButSelf",
						"common": "Team",
						"priority": 18,
						"hide": true,
						"broadcast": ["armin2", "krista2", "ymir2"],
						"broadcastmsg": "Your partner (Mikasa) has decided to kill ~Target~!",
						"msg": "'You don't stand a single chance to win unless you fight.' Mikasa looked at you with disdain as she sliced right through your neck."
					}
				},
				"initialCondition": {
					"curse": {
						"curseCount": 2,
						"cursedRole": "mikasa"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				},
				"kill": {
					"mode": {
						"ignore": [
							"krista2",
							"ymir2"
						]
					}
				}
			}
		},
		{
			"role": "armin",
			"translation": "Armin",
			"side": "village",
			"help": "Though not as physically adept as the others, you are a master tactician, so you can /inspect one person during the night! You are part of the First Division, and will convert if Keith assembles it. Be wary of claiming, because the Colossal Titan can outspeed bodyguards and the Smiling Titan can daykill.",
			"info": "Can inspect one person during the night. Part of the First Division. Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"inspect": {
						"target": "AnyButSelf",
						"common": "Self",
						"priority": 30
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "armin2",
			"translation": "Armin (3-D)",
			"side": "village",
			"help": "First Division, move out! In addition to being able to /inspect during the night, you can /examine to gain a second inspect that fails 20% of the time. (Note: The First Division is Mikasa, Ymir, and Krista). You will convert back in one night, so use your inspect wisely!",
			"info": "Can inspect one person during the night. Can examine (inspect) one additional person during the night with a 20% chance of failing.. Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"inspect": {
						"target": "AnyButSelf",
						"common": "Self",
						"priority": 30,
						"hide": true
					},
					"examine": {
						"command": "inspect",
						"target": "AnyButSelf",
						"common": "Self",
						"priority": 30,
						"hide": true,
						"failChance": 0.2
					}
				},
				"initialCondition": {
					"curse": {
						"curseCount": 2,
						"cursedRole": "armin"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				},
				"kill": {
					"mode": {
						"ignore": [
							"mikasa2",
							"krista2",
							"ymir2"
						]
					}
				}
			}
		},
		{
			"role": "sasha",
			"translation": "Sasha",
			"side": "village",
			"help": "Known as the 'potato girl' to the corps, you are simple-minded, but kind. You can identify distracters! You are part of the Second Division, and will convert if Keith assembles it.",
			"info": "Identifies distracters. Part of the Second Division. Sided with 104th Training Corps.",
			"actions": {
				"distract": {
					"mode": "identify",
					"msg": "Hello, ~Target~! Nice of you, the ~Role~, to stop by tonight!"
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "sasha2",
			"translation": "Sasha (3-D)",
			"side": "village",
			"help": "Second Division, move out! Now you ignore distracters and can /kill during the night, shared amongst your team (Jean, Marco, and Connie). You will convert back in one night, so use your kill wisely!",
			"info": "Can kill one person during the night (shared with Second Division). Ignores distracters. Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"kill": {
						"target": "AnyButSelf",
						"common": "Team",
						"priority": 18,
						"hide": true,
						"broadcast": ["jean2", "marco2", "connie2"],
						"broadcastmsg": "Your partner (Sasha) has decided to kill ~Target~!",
						"msg": "You didn't expect to be attacked /there/, but I guess that's Sasha's unconventionality for you..."
					}
				},
				"distract": {
					"mode": "ignore",
					"msg": "Someone distracted  you last night, but you were too busy eating to notice."
				},
				"initialCondition": {
					"curse": {
						"curseCount": 2,
						"cursedRole": "sasha"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				},
				"kill": {
					"mode": {
						"ignore": [
							"jean2",
							"connie2",
							"marco2"
						]
					}
				}
			}
		},
		{
			"role": "krista",
			"translation": "Krista",
			"side": "village",
			"help": "Seen by some in the corps as a 'goddess', you have the ability to /distract one person during the night! You are part of the First Division, and will convert if Keith assembles it. Your close friend Ymir may hax your /distract, so don't be afraid to use it!",
			"info": "Can distract one person during the night. Part of the First Division. Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"distract": {
						"target": "AnyButSelf",
						"common": "Team",
						"priority": 5,
						"distractmsg": "As you attempted to act during the night, Krista came and surprised you. She does look lovely in the moonlight... 'Hey, what are you looking at?' SMACK! With a slap to the face you blacked out."
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "krista2",
			"translation": "Krista (3-D)",
			"side": "village",
			"help": "First Division, move out! In addition to being able to /distract during the night, you share a /kill with the rest of the First Division (Mikasa, Armin, Ymir). You will convert back in one night, so use your kill wisely!",
			"info": "Can distract one person during the night. Can kill one person during the night (shared with First Division). Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"distract": {
						"target": "AnyButSelf",
						"common": "Team",
						"priority": 5,
						"hide": true,
						"distractmsg": "As you attempted to act during the night, Krista came and surprised you. She does look lovely in the moonlight... 'Hey, what are you looking at?' SMACK! With a slap to the face you blacked out."
					},
					"kill": {
						"target": "AnyButSelf",
						"common": "Team",
						"priority": 18,
						"hide": true,
						"broadcast": ["mikasa2", "ymir2", "armin2"],
						"broadcastmsg": "Your partner (Krista) has decided to kill ~Target~!",
						"msg": "Death is beautiful, isn't it? Is that an angel here to guide you to the afterlife? No, that was Krista who just put a blade through you."
					}
				},
				"initialCondition": {
					"curse": {
						"curseCount": 2,
						"cursedRole": "krista"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				},
				"kill": {
					"mode": {
						"ignore": [
							"mikasa2",
							"ymir2"
						]
					}
				}
			}
		},
		{
			"role": "ymir",
			"translation": "Ymir",
			"side": "village",
			"help": "A mysterious member of the corps, you are somehow close to Krista - er, Historia. Because of this, you can get hax on her distract, as well as the distract of some Titans! You are part of the First Division, and will convert if Keith assembles it.",
			"info": "Haxes distract. Part of the First Division. Inspects as a Titan to Zoe. Sided with 104th Training Corps.",
			"actions": {
				"hax": {
                    "distract": {
                        "revealTeam": 0.15,
                        "revealPlayer": 0.08
                    }
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is a Titan!"
				}
			}
		},
		{
			"role": "ymir2",
			"translation": "Ymir (3-D)",
			"side": "village",
			"help": "First Division, move out! You can still hax distracts, but you can also /kill during the night with your team (Mikasa, Armin, Krista). You will convert back after one night, so make your kill count.",
			"info": "Haxes distract. Can kill one person during the night (shared with First Division). Inspects as a Titan to Zoe. Sided with 104th Training Corps.",
			"actions": {
				"hax": {
					"distract": {
						"revealTeam": 0.15,
						"revealPlayer": 0.08
					}
				},
				"night": {
					"kill": {
						"target": "AnyButSelf",
						"common": "Team",
						"priority": 18,
						"hide": true,
						"broadcast": ["mikasa2", "krista2", "ymir2"],
						"broadcastmsg": "Your partner (Ymir) has decided to kill ~Target~!",
						"msg": "You thought that girl over there looked scared, so you went to take a look. Big mistake. Ymir appeared out of nowhere and her blade went right through your skin."
					}
				},
				"initialCondition": {
					"curse": {
						"curseCount": 2,
						"cursedRole": "ymir"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is a Titan!"
				},
				"kill": {
					"mode": {
						"ignore": [
							"krista2",
							"mikasa2"
						]
					}
				}
			}
		},
		{
			"role": "jean",
			"translation": "Jean",
			"side": "village",
			"help": "The foil character and rival to Eren, you never have a problem speaking your mind, so your combatant nature gives you a vote of -3. You'll know your good friend Marco from the start. You are part of the Second Division, and will convert if Keith assembles you.",
			"info": "Vote of -3. Knows Marco. Part of the Second Division. Sided with 104th Training Corps.",
			"actions": {
				"vote": -3,
				"startup": {
					"revealRole": ["marco"]
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "jean2",
			"translation": "Jean (3-D)",
			"side": "village",
			"help": "Second Division, move out! In addition to your vote of -3, you can /kill one person during the night, shared with your team (Marco, Sasha, Connie). You will convert back in one night, so use your kill wisely!",
			"info": "Vote of -3. Can kill one person during the night (shared with Second Division). Sided with 104th Training Corps.",
			"actions": {
				"vote": -3,
				"night": {
					"kill": {
						"target": "AnyButSelf",
						"common": "Team",
						"priority": 18,
						"hide": true,
						"broadcast": ["marco2", "connie2", "sasha2"],
						"broadcastmsg": "Your partner (Jean) has decided to kill ~Target~!",
						"msg": "'I could have been safe in the interior, but I just HAD to be here to deal with cretins like you!' Jean spat in disgust as he put you to an end."
					}
				},
				"initialCondition": {
					"curse": {
						"curseCount": 2,
						"cursedRole": "jean"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				},
				"kill": {
					"mode": {
						"ignore": [
							"sasha2",
							"marco2",
							"connie2"
						]
					}
				}
			}
		},
		{
			"role": "marco",
			"translation": "Marco",
			"side": "village",
			"help": "You're responsible for keeping the morale of the troops high, so your vote is 2! You'll also know your friend Jean from the start. You are part of the Second Division, and will convert if Keith assembles you.",
			"info": "Vote of 2. Knows Jean. Part of the Second Division. Sided with 104th Training Corps.",
			"actions": {
				"vote": 2,
				"startup": {
					"revealRole": ["jean"]
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "marco2",
			"translation": "Marco (3-D)",
			"side": "village",
			"help": "Second Division, move out! In addition to your vote of 2, you can /kill one person during the night, shared with your team (Jean, Sasha, Connie). You will convert back in one night, so use your kill wisely!",
			"info": "Vote of 2. Can kill one person during the night (shared with Second Division). Sided with 104th Training Corps.",
			"actions": {
				"vote": 2,
				"night": {
					"kill": {
						"target": "AnyButSelf",
						"common": "Team",
						"priority": 18,
						"hide": true,
						"broadcast": ["jean2", "connie2", "sasha2"],
						"broadcastmsg": "Your partner (Marco) has decided to kill ~Target~!",
						"msg": "Marco seemed hesitant to raise his blade. You thought you were getting off the hook this time. Then you saw it go right through you. 'Please forgive me...'"
					}
				},
				"initialCondition": {
					"curse": {
						"curseCount": 2,
						"cursedRole": "marco"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				},
				"kill": {
					"mode": {
						"ignore": [
							"sasha2",
							"jean2",
							"connie2"
						]
					}
				}
			}
		},
		{
			"role": "connie",
			"translation": "Connie",
			"side": "village",
			"help": "A light-hearted and outgoing member of the Training Corps, you can /shout to one person during the night to expose your role to them! You are part of the Second Division, and will convert if Keith assembles it.",
			"info": "Can shout at one person to reveal himself to them. Part of the Second Division. Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"shout": {
						"command": "dummy2",
						"common": "Self",
						"target": "AnyButSelf",
						"priority": 25,
						"dummy2targetmsg": "You heard Connie shouting at you from a distance. 'Hurry up, ~Target~, or else you'll fall behind!' Why does ~Self~ always have to be so pushy?",
						"dummy2usermsg": "You revealed your identity to ~Target~!"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "connie2",
			"translation": "Connie (3-D)",
			"side": "village",
			"help": "Second Division, move out! In addition to being able to /shout to one person during the night, you share a /kill during the night with your team (Jean, Marco, Sasha). You will convert back in one night, so make your kill count!",
			"info": "Can shout at one person to reveal himself to them. Can kill one person during the night (shared with Second Division). Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"shout": {
						"command": "dummy2",
						"common": "Self",
						"target": "AnyButSelf",
						"priority": 25,
						"hide": true,
						"dummy2targetmsg": "You heard Connie shouting at you from a distance. 'Hurry up, ~Target~, or else you'll fall behind!' Why does ~Self~ always have to be so pushy?",
						"dummy2usermsg": "You revealed your identity to ~Target~!"
					},
					"kill": {
						"target": "AnyButSelf",
						"common": "Team",
						"priority": 18,
						"hide": true,
						"broadcast": ["marco2", "jean2", "sasha2"],
						"broadcastmsg": "Your partner (Connie) has decided to kill ~Target~!",
						"msg": "'HEY YOU GUYS AIN'T STEALING MY THUNDER! THIS ONE IS MINE!' Who is that and why are they so loud? Must be Connie... Oh."
					}
				},
				"initialCondition": {
					"curse": {
						"curseCount": 2,
						"cursedRole": "connie"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				},
				"kill": {
					"mode": {
						"ignore": [
							"sasha2",
							"marco2",
							"jean2"
						]
					}
				}
			}
		},
		{
			"role": "levi",
			"translation": "Levi",
			"side": "village",
			"help": "Humanity's strongest soldier, you lead a squadron of the Survey Corps. You can /kill during the day with a 45% chance of revealing!",
			"info": "Can kill one person during the day with a 45% chance of revealing. Sided with 104th Training Corps.",
			"actions": {
				"standby": {
					"kill": {
						"target": "AnyButSelf",
						"msg": "You can now /kill during the day (you may be revealed)!",
						"killmsg": "Levi deftly appears out of nowhere with his 3-D manuever gear. Brandishing a pair of blades in his hands, he cuts through the neck of ~Target~, killing them effortlessly.",
						"revealChance": 0.45,
						"revealmsg": "~Self~ took a moment to clean his blades. 'Disgusting.'"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "mike",
			"translation": "Mike",
			"side": "village",
			"help": "A squad leader of the Survey Corps, your strength is second only to Levi. This means you counter all night actions - inspects, distracts, protects, and most nightkills (besides the kills of the Aberrant, Smiling, Beast, and Colossal Titan's smash). You also kill the first voter on your lynch wagon.",
			"info": "Kills distracters. Kills inspectors. Kills protectors. Counters nightkillers (besides the Aberrant, Smiling, Beast, and Colossal Titan [smash only]). Kills the first voter upon lynch. Sided with 104th Training Corps.",
			"actions": {
				"distract": {
					"mode": "ChangeTarget",
					"hookermsg": "You attempted to distract Mike during the night but he was too ruthless and sliced you up instead!",
					"msg": "Someone distracted you last night. In your fury you killed them before you could tell who they were."
				},
				"inspect": {
					"mode": "ChangeTarget",
					"targetmsg": "You attempted to inspect Mike during the night but he was too wary and sliced you up instead!",
					"msg": "Someone attempted to inspect you last night, but it's you who'll be doing the sniffing around here. You killed them before they got to know anything."
				},
				"protect": {
					"mode": "ChangeTarget",
					"hookermsg": "You attempted to protect Mike during the night but he doesn't need any help. You were killed instead.",
					"msg": "Someone attempted to protect you last night but others would only slow you down. So you killed them."
				},
				"kill": {
					"msg": "Someone attempted to kill you during the night. But you're just as skilled at killing...",
					"mode": "ChangeTarget"
				},
				"lynch": {
					"killVoters": {
						"first": 1,
						"message": "Mike's not going down without a fight, amd he's taking ~Target~ with him for giving the mob that idea!"
					}
				}
			}
		},
		{
			"role": "petra",
			"translation": "Petra",
			"side": "village",
			"help": "A member of the Survey Corps, you are both a strong fighter and a kind-hearted person. You evade nightkills, but have a vote of 0. Alternatively, you can /convert to a role that can reveal yourself during the day in order to connect PRs, but lose your nightkill evasion. You won't be killed in the day, however!",
			"info": "Evades nightkills. Vote of 0. Can convert into a role which can expose itself but lose nightkill evasion. Sided with 104th Training Corps.",
			"actions": {
				"kill": {
					"mode": "ignore"
				},
				"night": {
					"convert": {
						"target": "OnlySelf",
						"common": "Self",
						"priority": 2,
						"newRole": "petra2",
						"silent": true
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "petra2",
			"translation": "Petra",
			"side": "village",
			"help": "You evade daykills so you can still connect everyone by exposing yourself with the day with /expose, but you're vulnerable during the night and you can't be protected!",
			"info": "Evades daykills. Can't be protected. Sided with 104th Training Corps.",
			"actions": {
				"daykill": "evade",
				"protect": {
					"mode": "ignore"
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				},
				"standby": {
					"expose": {
						"target": "Self",
						"msg": "You can /expose yourself now!",
						"exposemsg": "Petra slipped up a bit when using her manuever gear and now everyone can see her. ~Self~ blushed slightly before darting off again."
					}
				}
			}
		},
		{
			"role": "erwin",
			"translation": "Erwin",
			"side": "village",
			"help": "The leader of the Survey Corps, you are a cunning strategist and you'll randomly know two village power roles from the start. Use this to your advantage to connect humanity!",
			"info": "Knows the identity of two power roles at random. Sided with 104th Training Corps.",
			"actions": {
				"startup": {
					"revealRole": ["eren", "mikasa"]
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "erwin2",
			"translation": "Erwin",
			"side": "village",
			"hide": true,
			"help": "The leader of the Survey Corps, you are a cunning strategist and you'll randomly know two village power roles from the start. Use this to your advantage to connect humanity!",
			"info": "Knows the identity of two power roles at random. Sided with 104th Training Corps.",
			"actions": {
				"startup": {
					"revealRole": ["krista", "ymir"]
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "erwin3",
			"translation": "Erwin",
			"side": "village",
			"hide": true,
			"help": "The leader of the Survey Corps, you are a cunning strategist and you'll randomly know two village power roles from the start. Use this to your advantage to connect humanity!",
			"info": "Knows the identity of two power roles at random. Sided with 104th Training Corps.",
			"actions": {
				"startup": {
					"revealRole": ["jean", "marco"]
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "erwin4",
			"translation": "Erwin",
			"side": "village",
			"hide": true,
			"help": "The leader of the Survey Corps, you are a cunning strategist and you'll randomly know two village power roles from the start. Use this to your advantage to connect humanity!",
			"info": "Knows the identity of two power roles at random. Sided with 104th Training Corps.",
			"actions": {
				"startup": {
					"revealRole": ["sasha", "connie"]
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "erwin5",
			"translation": "Erwin",
			"side": "village",
			"hide": true,
			"help": "The leader of the Survey Corps, you are a cunning strategist and you'll randomly know two village power roles from the start. Use this to your advantage to connect humanity!",
			"info": "Knows the identity of two power roles at random. Sided with 104th Training Corps.",
			"actions": {
				"startup": {
					"revealRole": ["keith", "armin"]
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "erwin6",
			"translation": "Erwin",
			"hide": true,
			"side": "village",
			"help": "The leader of the Survey Corps, you are a cunning strategist and you'll randomly know two village power roles from the start. Use this to your advantage to connect humanity!",
			"info": "Knows the identity of two power roles at random. Sided with 104th Training Corps.",
			"actions": {
				"startup": {
					"revealRole": ["levi", "petra"]
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				}
			}
		},
		{
			"role": "zoe",
			"translation": "Zoë",
			"side": "village",
			"help": "A scientist working with the Survey Corps, you have some strange fascination with Titans. As such, you can /inspect during the night to see if your target is a Titan or not! (Beware, as Eren and Ymir will inspect as Titans.)",
			"info": "Can inspect one person during the night to see if they are a Titan or not. Sided with 104th Training Corps.",
			"actions": {
				"night": {
					"inspect": {
						"command": "dummy",
						"common": "Role",
						"priority": 30,
						"target": "AnyButSelf"
					}
				}
			}
		},
		{
			"role": "titanpriority",
			"translation": "Titans",
			"side": "titan",
			"hide": true,
			"help": "nope",
			"info": "double nope",
			"actions": {
				"night": {
					"kill": {
						"target": "AnyButTeam",
						"common": "Role",
						"priority": 16
					}
				}
			}
		},
		{
			"role": "titan",
			"translation": "Titan",
			"side": "titan",
			"help": "A mindless, destructive being that seems to kill for the sake of killing. Use /kill during the night!",
			"info": "Can kill one person during the night (shared with the other regular Titans). Sided with Titans.",
			"actions": {
				"startup": "team-reveal-with-roles",
				"preventTeamvote": true,
				"teamTalk": true,
				"night": {
					"kill": {
						"target": "AnyButTeam",
						"common": "Role",
						"priority": 16,
						"hide": true,
						"broadcast": "team",
						"broadcastmsg": "Your partner (Titan) has decided to kill ~Target~!",
						"msg": "It's a Titan. Oh my god, it's a Titan. I'm going to die. I'm actually going to d- SNAP!"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is a Titan!"
				}
			}
		},
		{
			"role": "smile",
			"translation": "Smiling Titan",
			"side": "titan",
			"help": "A peculiar type of Titan that seems to always be smiling. You were the one responsible for killing Eren's mother! You can /chomp one person during the day to bring someone the same fate, and you won't be revealed! You can also /kill at night like a normal Titan and your creepiness allows you to kill exposers.",
			"info": "Can kill one person during the night. Can chomp (kill) one person during the day. Kills exposers. Sided with Titans.",
			"actions": {
				"startup": "team-reveal-with-roles",
				"preventTeamvote": true,
				"teamTalk": true,
				"night": {
					"kill": {
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 16,
						"hide": true,
						"broadcast": "team",
						"broadcastmsg": "Your partner (Smiling Titan) has decided to kill ~Target~!",
						"bypass": ["ChangeTarget"],
						"msg": "It's a Titan...staring really creepily at you. You were too fixated at its gaze to save yourself."
					}
				},
				"standby": {
					"chomp": {
						"command": "kill",
						"target": "AnyButTeam",
						"msg": "You can now kill with /chomp!",
						"killmsg": "The Smiling Titan scoops ~Target~ up with one hand, breaks their spine, and then bites their head off, making blood spew everywhere..."
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is a Titan!"
				},
				"expose": {
					"mode": {
						"revenge": ["keith"]
					},
					"msg": "Keith attempted to expose the Smiling Titan, but before he could YELL AT HIM AND ASK HIM HIS ROLE he was EATEN by the TITANS!"
				}
			}
		},
		{
			"role": "aberrant",
			"translation": "Aberrant Titan",
			"side": "titan",
			"help": "Unlike other Titans, you don't necessarily just kill humans - your actions have no pattern! Use this unpredictability to /distract one person during the night along with a /kill every night with your team.",
			"info": "Can kill one person during the night. Can distract one person during the night. Sided with Titans.",
			"actions": {
				"startup": "team-reveal-with-roles",
				"preventTeamvote": true,
				"teamTalk": true,
				"night": {
					"kill": {
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 16,
						"hide": true,
						"broadcast": "team",
						"broadcastmsg": "Your partner (Aberrant Titan) has decided to kill ~Target~!",
						"bypass": ["ChangeTarget"],
						"msg": "OH MY GOD WHY DOES THAT TITAN MOVE SO FAST AHHHH- *splat*"
					},
					"distract": {
						"target": "AnyButTeam",
						"common": "Self",
						"priority": 4,
						"broadcast": "team",
						"broadcastmsg": "Your partner (Aberrant Titan) has decided to distract ~Target~!"
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is a Titan!"
				}
			}
		},
		{
			"role": "beast",
			"translation": "Beast Titan",
			"side": "titan",
			"help": "Contrary to what your name may imply, you possess a modicum of intelligence that you used to interrogate humanity about the 3-D Manuever Gear, so along with your /kill every night, you can also /inspect during the night and /expose twice per game!",
			"info": "Can kill one person during the night. Can inspect one person during the night. Can expose one person during the day, twice per game. Sided with Titans.",
			"actions": {
				"startup": "team-reveal-with-roles",
				"preventTeamvote": true,
				"teamTalk": true,
				"night": {
					"kill": {
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 16,
						"hide": true,
						"broadcast": "team",
						"broadcastmsg": "Your partner (Beast Titan) has decided to kill ~Target~!",
						"bypass": ["ChangeTarget"],
						"msg": "This Titan almost looks like it's studying you as it takes you into its hands and drops you into its throat..."
					},
					"inspect": {
						"target": "AnyButTeam",
						"common": "Self",
						"priority": 30
					}
				},
				"standby": {
					"expose": {
						"target": "AnyButTeam",
						"msg": "You can now type /expose to reveal someone's role!",
						"exposemsg": "The Beast Titan captures ~Target~ by their manuever gear, revealing them as ~Role~ before letting them go!",
						"charges": 2
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is a Titan!"
				}
			}
		},
		{
			"role": "armored",
			"translation": "Armored Titan",
			"side": "titan2",
			"help": "A special Titan form, you stand 15 meters tall and first appeared during the breach of Wall Maria. As such, you evade nightkills and can /kill during the night. You will also be inspected as a Recruit.",
			"info": "Evades nightkills. Can kill one person during the night. Reveals as Recruit. Sided with Titan Shifters.",
			"actions": {
				"startup": "team-reveal-with-roles",
				"preventTeamvote": true,
				"teamTalk": true,
				"night": {
					"kill": {
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 17,
						"broadcast": "team",
						"broadcastmsg": "Your partner (Armored Titan) has decided to kill ~Target~!",
						"msg": "It's a Titan. Oh my god, it's a Titan. I'm going to die. I'm actually going to d- SNAP!"
					}
				},
				"kill": {
					"mode": "ignore"
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is a Titan!"
				},
				"inspect": {
					"revealAs": "recruit"
				}
			}
		},
		{
			"role": "colossal",
			"translation": "Colossal Titan",
			"side": "titan2",
			"help": "A monstrosity that stands 60 meters tall - so tall, you can look over the walls humanity built to keep you out. You are extremely powerful, so you have your own /smash kill every other night with very high priority in addition to the team /kill. You will also evade 35% of nightkills. When you die, the Female Titan will change form!",
			"info": "Can smash (kill) one person during the night, every other night, which outspeeds distracters and bodyguards. Evades 35% of nightkills. Can kill (shared with team) one person during the night. Converts Female Titan on death. Sided with Titan Shifters.",
			"actions": {
				"startup": "team-reveal-with-roles",
				"preventTeamvote": true,
				"teamTalk": true,
				"night": {
					"kill": {
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 17,
						"broadcast": "team",
						"broadcastmsg": "Your partner (Colossal Titan) has decided to kill ~Target~!",
						"msg": "It's 60 freaking meters tall. Did you really expect to survive an attack from the Colossal Titan? Didn't think so."
					},
					"smash": {
						"command": "kill",
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 2,
						"recharge": 2,
						"broadcast": "team",
						"broadcastmsg": "Your partner (Colossal Titan) has decided to smash ~Target~!",
						"bypass": ["ChangeTarget"],
						"msg": "The Colossal Titan looked at you menacingly before personally smashing you under his fist."
					}
				},
				"kill": {
					"mode": {
						"evadeChance": 0.35
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is a Titan!"
				},
				"onDeath": {
					"convertRoles": {
						"female": "female2"
					},
					"convertmsg": "The Colossal Titan has fallen, but the Female Titan has come to her full power in its wake!"
				}
			}
		},
		{
			"role": "colossals",
			"translation": "Colossal Titan",
			"side": "titan2",
			"help": "A monstrosity that stands 60 meters tall - so tall, you can look over the walls humanity built to keep you out. You are extremely powerful, so you can /smash during the night to have a high priority kill which outspeeds everything.",
			"info": "Can smash (kill) one person during the night, which outspeeds distracters and bodyguards. Sided with Titan Shifters.",
			"actions": {
				"startup": "team-reveal-with-roles",
				"preventTeamvote": true,
				"night": {
					"smash": {
						"command": "kill",
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 2,
						"hide": true,
						"broadcast": "team",
						"broadcastmsg": "Your partner (Colossal Titan) has decided to smash ~Target~!",
						"msg": "It's 60 freaking meters tall. Did you really expect to survive an attack from the Colossal Titan? Didn't think so."
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is a Titan!"
				}
			}
		},
		{
			"role": "female",
			"translation": "Female Titan",
			"side": "titan2",
			"help": "A Titan powerful enough to go toe-to-toe against the strongest of human fighters. You will inspect as a Recruit and you cannot be killed. You can /kill normally during the night. When the Colossal Titan dies, you will change form.",
			"info": "Can kill one perso nduring the night. Cannot be killed and inspects as a Recruit. Sided with Titan Shifters.",
			"actions": {
				"startup": "team-reveal-with-roles",
				"preventTeamvote": true,
				"teamTalk": true,
				"inspect": {
					"revealAs": "recruit"
				},
				"kill": {
					"mode": "ignore"
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is not a Titan!"
				},
				"night": {
					"kill": {
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 17,
						"broadcast": "team",
						"broadcastmsg": "The Female Titan (~Player~) has chosen to kill ~Target~!",
						"msg": "Well, she isn't exactly a femme fatale, but the Female Titan can still kick your butt. You stood no chance."
					}
				}
			}
		},
		{
			"role": "female2",
			"translation": "Female Titan",
			"side": "titan2",
			"help": "With the death of the Colossal Titan you can now /kill during the standby (nonrevealing) as well as during the night. You still inspect as a Recruit.",
			"info": "Can kill during the night. Can kill during the day (nonrevealing). Inspects as Recruit. Evades nightkills. Sided with Titan Shifters.",
			"actions": {
				"startup": "team-reveal-with-roles",
				"preventTeamvote": true,
				"teamTalk": true,
				"kill": {
					"mode": "ignore"
				},
				"standby": {
					"kill": {
						"target": "AnyButTeam",
						"msg": "You can kill now with /kill! You won't be revealed.",
						"killmsg": "The Female Titan stares down ~Target~ and prepares to fight. But the Female Titan was too fast and simply bashed ~Target~'s head into a tree, killing them instantly."
					}
				},
				"night": {
					"kill": {
						"target": "AnyButTeam",
						"common": "Team",
						"priority": 17,
						"hide": true,
						"broadcast": "team",
						"broadcastmsg": "The Female Titan (~Player~) has chosen to kill ~Target~!",
						"msg": "Well, she isn't exactly a femme fatale, but the Female Titan can still kick your butt. You stood no chance."
					}
				}
			}
		},
		{
			"role": "wall",
			"translation": "Wall Titan",
			"side": "titan3",
			"help": "Little is known about you at this point in time, but you make up the walls that enclose humanity. For some convoluted reason you have 9999 votes and evade nightkills 73% of the time because you're in a wall, but you are prone to being daykilled.",
			"info": "Vote of 9999. Evades nightkills 73% of the time. Sided with Wall Titan.",
			"winIfDeadRoles": [
				"eren2",
				"erent",
				"levi",
				"mikasa2",
				"armin2",
				"krista2",
				"ymir2",
				"jean2",
				"marco2",
				"connie2",
				"sasha2",
				"titan",
				"smile",
				"aberrant",
				"beast",
				"armored",
				"colossal",
				"female",
				"keith",
				"mike"
			],
			"actions": {
				"vote": 9999,
				"kill": {
					"mode": {
						"evadeChance": 0.73
					}
				},
				"dummy": {
					"mode": "ignore",
					"msg": "Your target is a Titan!"
				}
			}
		}
	],
	"roles1": [
		"titan",
		"eren",
		"recruit",
		"recruit",
		"recruit",
		"connie",
		"titan"
	],
	"roles2": [
		"mikasa",
		"titan",
		"krista",
		"recruit",
		"armin",
		"titan",
		"colossal",
		"keiths",
		"recruit",
		"eren",
		"armored",
		"ymir",
		"recruit"
	],
	"roles3": [
		"mikasa",
		"titan",
		"krista",
		"titan",
		"armin",
		"recruit",
		"colossal",
		"keith",
		"ymir",
		"eren",
		"recruit",
		"armored",
		"jean",
		"marco",
		"smile",
		"levi",
		"female",
		"recruit",
		"mike",
		"aberrant",
		"connie",
		"wall",
		"sasha",
		"petra",
		"recruit",
		"beast",
		{
			"erwin": 1,
			"erwin2": 1,
			"erwin3": 1,
			"erwin4": 1,
			"erwin5": 1,
			"erwin6": 1
		},
		"recruit",
		"zoe",
		"titan",
		"eren",
		"recruit",
		"keith",
		"recruit",
		"smile",
		"colossal",
		"levi",
		"recruit",
		"recruit",
		"mikasa"
	],
	"villageCantLoseRoles": [
		"marco",
		"marco2",
		"erent",
		"eren2",
		"mikasa2",
		"jean2",
		"krista2",
		"ymir2",
		"connie2",
		"sasha2",
		"levi",
		"keith"
	],
	"tips": {
		"Claiming": "Don't do it unless Colossal Titan and Smiling Titan are out of the game.",
		"Krista": "Spam your /distract command. Ymir can hax it.",
		"3-D roles": "Watch to see who your teammates are attacking. If someone doesn't die when you target them, or changes the kill quickly, they're likely on your side.",
		"Mike": "Attract attention, but don't be glaring obvious (look everybody I am a bomb, please kill me).",
		"Jean": "You're as safe of a claim as anyone. Get Marco to vote anyone who tries to vote you because people nowadays don't know what selfvoting to prove negative voter means."
	},
	"changelog": {
		"3.17.14": "Gave Keith an expose every other day. Colossal Titan evades 35% of nightkills. Added Mike (counters all night actions and votebombs first voter).",
		"3.18.14": "Armored Titan inspects as Recruit. Smiling Titan kills exposers.",
		"6.4.14": "Female Titan now evades nightkills in her second form.",
		"6.21.14": "Fixing up priority list + typos.",
		"6.28.14": "Added tips."
	}
}
		
