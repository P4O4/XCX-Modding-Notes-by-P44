# PR0FILE_4O4 XCX MODDING NOTES [[TCRF version here](https://tcrf.net/Notes:Xenoblade_Chronicles_X)]
___
### Tools used:
* Unpack /content CPKs with [**CriPakTools**](https://github.com/esperknight/CriPakTools)' Decompress
* Repack with [**Repacker CPK**](http://www.mediafire.com/file/osutzusowu5m6h8/Repacker_CPK.zip/file) (uncheck ForceCompress)
* Other tools mentioned when necessary
### [File extensions reference](https://forum.xentax.com/viewtopic.php?t=17956): camdo=model , camst=texture, etc.
___
### Doable:
* music, movies, sfx edits
* some model swaps (skells,faces...)
### To do:
* manage to reimport edited textures
* repack ma9990.casmda! (map files)
___
## .../action.cpk
*  movement/battle animation scripts (seen on hexedit)]
	* MCA
```	
	/dl: DOLLS(SKELLS)
	/en: ENEMIES
	/mb: MOBs(NLA-only NPCs)
	/ni: ??? (LB/AN bindpose/oneshot/loop scripts)
	/np: NPCs
	/oj: OBJECTS
	/pc: PARTY CHARACTERS
	/pt: PARTY TATSU
	/wd: WEAPON(ARTS) [DOLLS(SKELLS)]
	/we: WEAPON(ARTS) (ENEMIES)
	/ws: WEAPON(ARTS) (PLAYER)
```

### Modding notes:
* editing/removing/swapping seems to always crash
___
## .../bdat.cpk
* binary data
	* BDAT
	```
	common_local_us.bdat
	/us/qev: quest scenes
	/us/tev: text-only scenes?
	/us/xs:  main story scenes
	```
___
## ...chr_dl.cpk
* doll(skell) models
	* CAMDO,CAMTP,CASMT,CEA,CES,EFP,HKT
	
	```
	dl019100.camdo: 'beta' Ares
	```
	
### Modding notes:
* No way to reimport edited textures
* Swapping 'beta' Ares crashes
* Swapping others is jank (animations break model)
	* Swap animations on hkc.cpk
* *.hkt* references the original rig name in the file
	* Change to swapped name in hexedit just in case
___
## .../chr_en.cpk
* enemy models/effects
	* CHR,CADYS,CAMDO,CAMTP,CASMT,CEA,CES,EFP,HKT
*couldn't figure out naming rules, but seems to have the same names as stream/voice/en*
* bigger files are usually bosses
* .cadys only exist for a few enemies?
* some ganglions as en02___

	```
	en010301= Vita
	en010601: Vasara
	en010701: Zu Pharg [named Aegis]
	en010801: Almandal
	en061101: Chimera Lao
	```
___
## .../chr_fc.cpk
* character faces and hairs
	* CADYS,CAMDO,CAMTP,CASMT,EFP,HKT
		
* fc1__=male	fc2__=female
* fcXN___:  N is a face group
	* fcXN1__=faces, fcXN2__=hairs, fcXN3__=ahoges
	
* Male MCs are under fc11,12,13:
* Other Playable male characters under fc18__:
	```
	fc181000	Blank face
	fc181010	Nagi's face
	fc182010	Nagi's hair
	fc181020	L's face
	fc181030/31 	Lao's face	(Duplicate?)
	```	

* Same goes for female but with fc2__ instead


	```
	fc281010 	Elma
	fc281011	True Form Elma
	fc281020 	Lin
	```
		
### Modding notes:
* UNPACK camdo/casmt:
	* XenoMax.dlu/Xenotoolset
* REPACK:
	* ???
* camdo/camst swaps (renaming) are possible
* The game runs even with the folder missing
* Skin color (i.e elma's true form or vandham) seems to be hardcoded into the game
___

## .../chr_fceye.cpk
* Textures for MC's eyes
	* CATEX 
### Modding notes:
* UNPACK:
	* Use xenoTextureConvert (Xenotoolset)
* REPACK:
	* ????	
___
## .../chr_fctex.cpk
* Textures for MC's face details:
	* CATEX 
* IDs correspond to model IDs
* fc1___= male, fc2___= female
* __a__= natural feature, __b__= face paint
### Modding notes:
* UNPACK:
	* Use xenoTextureConvert (Xenotoolset)
* REPACK:
	* ????	
___
## .../chr_mb.cpk
* NPC files (NLA only?)
	* CAMDO,CAMTP,CASMT,CEA,EFP,HKT
	```
	mb0110__	 male blades
	mb0111__	 male civillian
	mb0120__	 female blades
	mb0121__	 female civillian
	
	mb02__  manon
	... (other races)
	mb08__ 	nopon
	```
___
## .../chr_np.cpk
* NPC files
	* CHR,CADYS,CAMDO,CAMTP,CASMT,CEA,CES,EFP,HKT
	```
	np002001	 Nagi's body
	np002101	 Vandham
	np002201	 Maurice
	np002501	 Celica's body
	np003101	 Gwin
	np005001	 Rock
	np006101	 Luxaar
	np006201	 Ga jiarg
	np006301	 Ga buidhe
	np006401	 Goethia
	np006501	 Dagahn 
	np006601	 Ryyz
	np007001	 Black Knight (ending beach scene character)
	np009001	 Tatsu
	np009101	 Tatsu (no hood)
	
	np01__: males
	np02__: females
	np03__: manon
	np04__: ganglion
	...(other races)
	
	np1015_: cat
	np1016_: dog
	```
___
## .../chr_oj.pkb
* Object files
	* CADYS,CAMDO,CAMTP,CASMT,CEA,CES,EFP,HKT
	```
	oj010001	Comm device [READABLE LORE IN TEXTURE (see appendix below)]
	oj020013	Manon ship
	oj050007	Shoulder from that chap5 scene
	oj090004	Lao from end beach scene
	oj250020	Tatsu (Low Quality)
	oj310011	White Whale
	oj490033	Full Lin (Low Quality)
	oj490034	Full Elma (Low Quality)
	oj490035	Full Cross (Low Quality)
	oj820102	Wrecked car
	oj820202	Container
	oj840045/6	Car
	oj840139	Rock
	oj840244	Nopon Monado
	
	oj87____	Holograms
		e.g:oj870031=	Wrothian holding cat
	```
___
## .../chr_pac.cpk
```
	datpac.capac
	rigpac.capac
```
___
## .../chr_pc.cpk
* Playable character files
	* CHR,CADYS,CAMDO,CAMTP,CASMT,CEA,CES(sounds),CRV(jump),EFP,HKT
* separated by body area (armour)
	```
	pc060201= L's default body
	pc070201= Celica's default body (one of the 2 to have .cadys and .efp too)
	pc299112= female blade suit
	pc271112 to pc271912= full female sets
	```
* pc1__= male	pc2__= female
* pcXXNNN_:
	* XX= armour set
	* NNN= armour subset
	```
	pc____1	 head
	pc____2	 torsos
	pc____3	 left arms
	pc____4	 right arms
	pc____5	 legs
	e.g:
	pc2131XX	 Irina's gear
	pc2132XX	 Lin's gear
	pc114XXX	 Lao's gear
	pc221XXX	 Elma's gear
        pc2241XX	 True Form Elma gear
	pc100XXX	 shirtless male
	```
___
## .../chr_pt.cpk
* Tatsu
	```
	clipevt_pt.cea
	```
* Checked on hexedit: references to:
	* battle/attack/arts/reload animations
	```
	pt009001.chr
	```
___
## .../chr_un.cpk
* Headgear
	* CAMDO,CASMT
	```
		un02_	  	glasses (un020080102 is a mask)
		un03_		snouts
		un04_		ears
		un07_		eyepatches
		un11_		head flowers
	```
___
## .../chr_wd.cpk
* Doll(skell) weapons
	* CAMDO,CAMTP,CASMT,EFP,HKT
* wdNN__A:
	* A: side indicated by 'l' or 'r'
	* NN:weapon class
	
* Classes(Not sure!):
	* 01:spare
	* 02:arms
	* 03:back
	* 04:shoulder
	* 06:both shoulders / temporary?
		
```
wd200201r to wd201401r:  Super weapons
```
___
## .../chr_wdb.cpk
* Doll(skell) temporary objects? e.g. missiles
	* CAMDO,CASMT,EFP
___
## .../chr_we.cpk
* Enemy weapons
	* CAMDO,CAMTP,CASMT,EFP,HKT
___
## .../chr_ws.cpk
* Playable characters' weapons
	* CADYS,CAMDO,CAMTP,CASMT,CAWDY,EFP,HKT
* ws1__=guns, ws2__= blades
* 'l' (left) and 'r' (right) side indicators
* Structure : wsXXYNNN

* XX seems to indicate class according to weapon_limit.cawdy
	```
	 #ws11 		Assault Rifle
	 #ws12 		Sniper Rifle
	 #ws13 		Dual guns 
	 #ws14 		Gatling gun
	 #ws15 		Raygun
	 #ws16 		Psycho launcher
	 #ws17 		unused??? (only few weapon models from Grenada Galctic Group)
	 #ws21 		Longsword
	 #ws22 		Javelin
	 #ws23 		Dual Swords
	 #ws24 		Shield
	 #ws25 		Knife
	 #ws26 		Photon Saber
	```
* Y seems to indicate the manufacturer 
	```
	 1 	 Sakuraba Industries
	 2 	 Grenada Galactic Group
	 3 	 Meredith & Co
	 4 	 Candid & Credible
	 5 	 Six Stars
	 6 	 Orphean Technologies
	 7 	 Nopon Commerce Guild
	 8 	 Factory 1.21
	```
* NNN indicates the model ID (there usually are 7 variant of the same model)
	```
	e.g:
	ws132101	 elma's gun ==> Dual Guns / Grenada Galactic Group / Model 1 / Variant 1
	ws215104	 katana ==> Longsword / Six Stars / Model 1 / Variant 4
	ws121101	 lao's sniper ==> Sniper Rifle / Sakuraba Industries / Model 1 / Variant 1
	```
___
## .../eff.cpk
* Effect bundles
	```
	/efb
		EFB,EPACS
		/btl	(en,wd,ws)
		/cf		(cas,ecas,ma,sky)
		/cmn
		/us
		common_mbo.efb
	/tuto/us
		EFB files (reference .txt)
	shaders.sha
	stencil.csvb
	```
___
## .../ev.cpk

#### /actor
* (?) Checked on hexedit, mentions: IDLEBT_STARTBT_IDLEBT_END]
	* CSVB
#### /cam
* Camera effects (noise)
	* EVA
#### /eff
* timeslot, weather
	* CSVB
#### /motion/oj/oj010001:
* Calls Comm device animations
	* HKT
#### /scn/us: 
* qev, xs scripts? (hexedit: references other ev files)
	* EVPA
#### /se/us: 
* Wind(?) sounds
	* ACB
#### /stm
* qev and xs animation table/containers
	* MDLSTM, MOTSTM, MOTSTM_DATA
###### /stm/us
* qev and xs audio
	* ADX			
* qev: sidequests (celica,nagi,skell)
* xsNN: chapter cutscenes (NN=chapter)
#### /title
* Files for title screen
	* CAEH,EFB,EVA,HKT
___
## .../gimmick.cpk
* various numbered folders with:
	* GIMK
	* 'popdata' for effect,enemy,item,se,tbox,npc,mapobj,event,arealock,door,bladeguide...
	* 'locationdata'
	
world_info.bin (on hexedit: calls '.gimk's)
___
## .../hkc.cpk
* Controls battle animations
* folders: dl,en,mb,np,oj,pc,pt,wd,we,ws
	
* SAR -> UNPACK:quickbms -> HKT
e.g:
/dl/dl019600.sar->000000_idle_anm.hkt(run, jump, arts animations)

### Modding notes:
* Import: using HavokMax 3dsmax plugin (https://github.com/PredatorCZ/HavokMax)
* When importing hkt and camdo files separately with xenomax and havokmax 3dsmax plugins, both anim\rig and model must be the same scale, preferrably 100
___
## .../map.cpk
* Mira files
	* CANVDA,CANVHE,CASMDA,CASMHD	
### /ma9990.casmda (UNPACK:XenoTools)
	```
	skybox0.camdo (crashes 3dsmax, too big)
	ma9990.cems
	ma9990.lcmd
	/collision (HKX)
	/effects (EPAC)
	/objects (CAMDO, CASMT)
		0	=NLA
		1,2...	=NLA details (roads, gates, some buildings...)
		6	=oblivia ring
		24	=lifehold units
		83	=forest?
		94	=trees
		90	=building
		91	=barracks
		31	=hangar?
		8	crashes 3dsmax, too big
	/terrain (CAMDO, CASMT)
		1	=primordia
		2	=oblivia
		3	=noctilum
		5	=cauldros
		6	=sylvalum
	/terrainLOD (CAMDO)
		3dsmax can't open files
	/textures (DDS)
		0125	=ECP logo
		/165	=lava
	/TGLD
		???
	```
### Modding notes:
* CAN'T, BUT BEING ABLE TO REPACK THESE WOULD BE AMAZING
___
## .../menu.cpk
* scripts (artsset,battlepoints,hud,network,system,...)
	* BMN
### /binary:
		minimap_info.cbin
### /bmn:
		.bmn scripts (collepedia,dollgarage,avatarmake,...)
### /env:
		.calgt avatar files
### /font:
		.fnt fonts (adams,caption,eurasia,normal,title_e)
### /motion:	
		folders: dl,en,pc
		.sar files -> quickbms-> .hkt animation scripts
### /shader:
		.gsh files
### /staffroll:
		.catex logos, .casfb credits
### /tex:
		.catex icons
### /vc:
		.bmv files
___
## .../monolib.cpk
```
	system.bin (sound configs)
	.../shader
		/ft: .calut files
		CA__._ textures/shaders
```
___
## .../movie
* USM scenes
### Modding notes:
* Extract: VGMToolbox video demultiplexer
	* ADX cutscene sound
	* M2V cutscene video
*Custom replace:
	* .avi -> Scaleform VideoEncoder->.usm
___
## .../script.cpk/us
* SB scipts (qev,tev,xs,enemy act/ai,...)
___
## .../snd.cpk:
* ACB sound banks
	```
	/btl[battle](en,wd,ws)
	/cf			(dl,map,np,oj,weather)
	/voice		(m,pc)
		e.g: np005001= footsteps
	commom.acb
		e.g:cmn_001_501_01: explosion
	```
### Modding notes:
* UNPACK:	
	* use AcbEditor (or vgmtoolbox\eternityaudiotools) on .acb (->.dsp)
	* use vgaudio on .dsp (->.adx)
* REPACK mods:
	* use PesConverter\AtomENCD on mp3 to adx
	* use vgaudio on .adx (->.dsp)
	* use AcbEditor on .dsp and original .acb (vgmtoolbox can't)
___
## .../stream
### /bgm:
* ADX background music
* xs___:  cutscene bgm
	* xNN_MM: OST, NN=song, MM=variant
		```
		e.g.:
		x12_00   	briefing
		x42		tatsu
		x43_00		melancholia
		x45_00		black tar
		x49_00		wir fliegen
		x79_00		dont worry
		x53_00		uncontrollable
		x63/x64		NLA
		x65/x66		primordia
		x67/x68		noctilum
		x69/x70		oblivia
		x71/x72		sylvalum
		x73/x74		cauldros
		```
		
### /ev_voice/sev/us:
* mXX and qXXX folders with ADX files
	* numbered chronologically
	* m= main, q= quests
```
	/voice
		/en/us
			ADX enemy voice line folders
			
		/mb/us
			ADX [NLA pass-by lines]
			
		/np/us
			ADX [NPCs]
			
		/pc/us
			ID folders for playable characters
			ADX [arts,btl,dw,soul]
			
			2-10:  Male MC
			
			3	 Studious (Goro Akechi-Robbie Daymond)
			6	 Heroic (Yosuke Hanamura-Yuri Lowenthal)
			7	 Rookie (Eren Yeager-Bryce Papenbrook)
			8	 Classic (Shulk-Adam Howden)
			
			21-29: Female MC (28:fiora)
			
			41	Nagi
			42	L
			43	Lao
			44	H.B. 
			45	Gwin
			46	Frye
			47	Doug
			48	Yelv
			49	Boze
			50	Phog
			51	Elma
			52	Lin
			53	Celica
			54	Irina 
			55	Murderess
			56	Alexa
			57	Hope
			58	Mia
			59	Tatsu (Japanese version only!)
```
### Modding notes:
* SWAP/REPLACE ADX
	* Use PesConverter on *mp3* to *adx*
___
## .../zone.cpk
* ATR	[???]
* ZNS	[hexedit:reference to enemies]
___
## Appendix:

![alt text](https://tcrf.net/images/b/be/XCX-CommDevTex.png)
___
PS.:Mass swaps with *Replace-O-Matic* (missing link) 
PS.:Some WiiU Gecko hacks exist but this is a Cemu project ¯\_(ツ)_/¯ 

