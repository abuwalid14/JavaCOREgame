# JavaCOREgame
تمرين خاص بلغة الجافا 

1.	Game Description

Champions of Rare Earth (CORE) is a strategy game. The current prototype provides a very simplified version of the game for one player. Here is the briefing provided to a player of this version of the game: 

"You are the ruler of the magical kingdom of Rare Earth. Rather than waging wars, every 4 years you and your enemies meet for a tournament where your champions figth challenges challenges. Prizes are money rather than territory or lives. You must assemble a team of champions who can meet (and hopefully win) challenges against your enemies. The game provides a collection of champions who can join your team."

As the ruler, you have a fixed amount of money (1000 gulden) in your treasury which can be used to assemble your team of champions and pay their entry fee for the tournament. Once you have a team, you will be expected to meet some challenges. Winning a challenge will bring you rewards, and increase your treasury. If you lose a challenge, you have to pay the reward money to your enemy and lose it from your treasury. At any point in the game, you can enter or retire champions from your team. If you retire a champion, you get back half of their tournament entry fee. So when you need money, you can retire champions (if they are in your team, but not if they are dead or retired). The skill in this version is in assembling your team in a way which enables you to win challenges and increase your treasury. 

Your enemies offer different types of challenges. Each challenge has a unique number, the name of the enemy, a type (Magic, Fight or Mystery), a required skill level, and a reward. In this game prototype, you will need to select a challenge by number (later versions will select challenges for you, at random). Your game should then choose the first available champion in your team who can meet the challenge and compare the skill levels. The results of meeting a challenge will be one of the following:
0.	“Challenge won by...“ – adds reward to treasury, return name of champion 
1.	“Challenge lost on skill level” - deducts reward from treasury, and set your champion to "dead"
2.	“Challenge lost as no suitable champion available” – deducts reward from treasury
3.	"Challenge is lost and player completely defeated" - deducts reward from treasury
-1.    "No such challenge"

Champions can be one of the following types: Wizard, Warrior or Dragon (more types to be added later). The table below shows which type of challenge they can meet:
	Magic	Fight	Mystery
Wizard	yes	yes	yes
Warrior	no	yes	no
Dragon	no	yes	Only if they talk

Each champion has a unique name, a skill level, an entry fee. Wizards have an entry fee of 300 gulden, but if they are also necromancers their fee is 400 gulden. They also have a speciality spell. Warriors set their own entry fee, and you need to store their preferred weapon. Dragons have a fixed entry fee of 500 gulden, and some of them can talk. Each champion has a skill level recorded as a number from 1 to 10. All dragons have a skill level of 7.  A warrior's skill level is their entry fee divided by 100 (ignoring remainders). Individual Wizards have different skill levels. 
See Appendix A for sample data.

A champion is in one of the following states:
•	waiting – in the game’s collection of champions, but not yet part of your tournament team
•	entered – has been entered in your team (entry fee paid) and is available to meet challenges
•	dead – is not available for challenges and cannot be retiren from the tournament 

Challenge numbers should be sequential from 1. Challenges can be fought more than once.

After losing a challenge, your treasury may be < 0. You cannot enter any more champions. However, you can continue to meet challenges with your remaining champions in the hope of winning some more money (even if your treasury goes further into debt). You may also make money by retiring champions. However, if your treasury has no money or is in debt, and you have no champions left to retire, you have lost the game and a suitable message should be output. 

2.	Scope 
This early working version of the game requires the player to select the challenge (by number). This has been done to make it possible to design a standard set of tests. Programs with "random" features are difficult to test because of their unpredictability. Once the game is fully tested, a “random” element can be introduced. You are NOT required to do this.

In future, the condition for "winning" the game will be to meet all the challenges and still have money left in the treasury. You are NOT required to implement this feature of the game.

In future, when the player has lost, the game will automatically terminate after displaying an appropriate message. You are NOT required to ensure the game terminates, but will be expected to display a suitable message.


3.	Functional Requirements  
When a player starts the game, they will be asked for their name. The system will create an instance of the game and automatically load all the sample data (see Appendix A) of champions and challenges into appropriate variables/collections, and set the treasury to 1000 gulden. 

The player should be able to create their team by entering some of the available champions into the tournament as part of their team. On entering a champion, appropriate deductions should be made from treasury to pay for their entry fee. If there is not enough money in the treasury or the champion not available, the champion cannot be entered. Appropriate messages about the outcomes should be displayed. 

A player can choose to fight challenges. In this prototype, the player will be required to provide a challenge number. The system will then select the first appropriate champion which can be used to meet that type of challenge. The result of the challenge will be processed as described above and a suitable message displayed. In this version, challenges may be fought more than once, and the player may view any or all of the challenges.

The player may enter or retire champions at any point in the game. Note: champions who are dead cannot be retiren or used to fight challenges. The player may also request to see: the state of the game, the state of their treasury, details of all champions still available for entry, details of all the champions in their team, details of all challenges, the state of one champion or challenge. 

These functional requirements are specified in the interface CORE
