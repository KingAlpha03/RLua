local service = setmetatable({}, {
__index = function(t, k)
return game:GetService(k)
end
})

local Walk=100
local Jump=100
function config()
	game.Players.LocalPlayer.Character.Humanoid.Name = "1"
	local l = game.Players.LocalPlayer.Character["1"]
	l.Parent = game.Players.LocalPlayer.Character
	l.Name = "Humanoid"
	wait(0.1)
	game.Players.LocalPlayer.Character["1"]:Destroy()
	game.Workspace.CurrentCamera.CameraSubject = game.Players.LocalPlayer.Character
	game.Players.LocalPlayer.Character.Animate.Disabled = true
	l.Changed:Connect(function()
		if l then
			l.WalkSpeed=Walk
			l.JumpPower=Jump
		end
	end)
end


local lt2hub = Instance.new("ScreenGui")
local scriptframe = Instance.new("Frame")
local autodupe = Instance.new("TextButton")
local admin = Instance.new("TextButton")
local jpower = Instance.new("TextButton")
local sellplanks = Instance.new("TextButton")
local sideland = Instance.new("TextButton")
local normland = Instance.new("TextButton")
local ozhub = Instance.new("TextButton")
local harddrag = Instance.new("TextButton")
local tpgift = Instance.new("TextButton")
local speed = Instance.new("TextButton")
local tpplanks = Instance.new("TextButton")
local stopland = Instance.new("TextButton")
local fly = Instance.new("TextButton")
local dupe = Instance.new("TextButton")
local stopdupe = Instance.new("TextButton")
local credits = Instance.new("TextLabel")

lt2hub.Name = "lt2 hub"
lt2hub.Parent = game.CoreGui

scriptframe.Name = "scriptframe"
scriptframe.Parent = lt2hub
scriptframe.Active = true
scriptframe.BackgroundColor3 = Color3.new(0.258824, 1, 0.976471)
scriptframe.Draggable = true
scriptframe.Position = UDim2.new(0.0940325558, 0, -3.7252903e-09, 0)
scriptframe.Selectable = true
scriptframe.Size = UDim2.new(0, 278, 0, 298)
scriptframe.Style = Enum.FrameStyle.RobloxRound

autodupe.Name = "autodupe"
autodupe.Parent = scriptframe
autodupe.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
autodupe.BorderSizePixel = 0
autodupe.Position = UDim2.new(0.06849204, 0, 0.498322189, 0)
autodupe.Size = UDim2.new(0, 101, 0, 19)
autodupe.Font = Enum.Font.Code
autodupe.Text = "AutoDupe"
autodupe.TextColor3 = Color3.new(0, 0.0980392, 1)
autodupe.TextScaled = true
autodupe.TextSize = 25
autodupe.TextWrapped = true
autodupe.MouseButton1Down:connect(function()
Screen = Instance.new("ScreenGui",game.Players.LocalPlayer.PlayerGui)
Scrolling = Instance.new("ScrollingFrame",Screen)
Scrolling.Size = UDim2.new(0,300,0,500)
Scrolling.CanvasSize = UDim2.new(0,300,3,0)
Exit = Instance.new("TextButton", Scrolling)
Exit.Size = UDim2.new(0,30,0,20)
Exit.Position = UDim2.new(1,-40,0,0)
Exit.Text = "Exit"
DontTP = Instance.new("TextButton", Scrolling)
DontTP.Size = UDim2.new(0,40,0,40)
DontTP.Position = UDim2.new(1,-60,0,50)
DontTP.Text = "Don't TP back"
DontTP.TextWrapped = true
DontTPVar = false
DontTP.MouseButton1Click:connect(function()
	DontTPVar = true
end)
Exit.MouseButton1Click:connect(function()
	Screen:Destroy()
end)
g = 0
Sniggle = false
gg = {}
function Start()
Sniggle = true
for i,v in pairs(game.Workspace.PlayerModels:GetChildren()) do
	if v:FindFirstChild("Owner") and v.Owner.Value == game.Players.LocalPlayer then
		if v:FindFirstChild("TreeClass") then
			game:GetService("RunService").RenderStepped:wait()
			if Scrolling:FindFirstChild(v.TreeClass.Value) then
				if not gg[i] then
					Scrolling[v.TreeClass.Value.." Value"].Value = Scrolling[v.TreeClass.Value.." Value"].Value+1
					Scrolling[v.TreeClass.Value].Text = v.TreeClass.Value.." ("..Scrolling[v.TreeClass.Value.." Value"].Value..")"
				end
			else
				g = g+1
				TreeButton = Instance.new("TextButton",Scrolling)
				TreeButton.Size = UDim2.new(0,100,0,50)
				TreeButton.Position = UDim2.new(0,10,0,70*g)
				TreeButton.Name = v.TreeClass.Value
				TreeButton.Text = v.TreeClass.Value.." (1)"
				TreeButton.MouseButton1Click:connect(function()
					Scrolling.Visible = false
					TP(TreeButton.Name)
				end)
				TreeVal = Instance.new("NumberValue",Scrolling)
				TreeVal.Name = v.TreeClass.Value.." Value"
				TreeVal.Value = 1
				gg[i] = v.TreeClass.Value
			end
		end
	end
end
end
if not Sniggle then
	Start()
end
--[[game.Workspace.PlayerModels.ChildAdded:connect(function(Item)
	Item:WaitForChild("Owner")
	if Item.Owner.Value == game.Players.LocalPlayer then
		Start()
	end
end)]]
game.Workspace.PlayerModels.ChildRemoved:connect(function(Item)
	if Item:FindFirstChild("Owner") and Item.Owner.Value == game.Players.LocalPlayer and Item:FindFirstChild("TreeClass") and Scrolling[Item.TreeClass.Value.." Value"] then
		Scrolling[Item.TreeClass.Value.." Value"].Value = Scrolling[Item.TreeClass.Value.." Value"].Value-1
		if Scrolling[Item.TreeClass.Value.." Value"].Value == 0 then
			Scrolling[Item.TreeClass.Value]:Destroy()
			Scrolling[Item.TreeClass.Value.." Value"]:Destroy()
		else
			Scrolling[Item.TreeClass.Value].Text = Item.TreeClass.Value.." ("..Scrolling[Item.TreeClass.Value.." Value"].Value..")"
		end
	end
end)

function TP(Name)
	sendNotice = game.ReplicatedStorage.Notices.SendUserNotice
	sendNotice:Fire("Click on a whitelisted base")
	local ButtonPress
	ButtonPress = game.Players.LocalPlayer:GetMouse().Button1Down:Connect(function()
		Square = game.Players.LocalPlayer:GetMouse().Target
		if (Square.Name == "OriginSquare" or Square.Name == "Square") then
			ButtonPress:Disconnect()
			game.ReplicatedStorage.LoadSaveRequests.RequestSave:InvokeServer(game.Players.LocalPlayer.CurrentSaveSlot.Value)
			local success, errorMessage = game.ReplicatedStorage.LoadSaveRequests.RequestLoad:InvokeServer(game.Players.LocalPlayer.CurrentSaveSlot.Value,game.Players.LocalPlayer)
			if success then
				print'Initial Reload Success'
				sendNotice:Fire("Reload success", 0.8)
				game.Players.LocalPlayer.CurrentSaveSlot.RobloxLocked = true
				game.Players.LocalPlayer.CurrentSaveSlot.Set.RobloxLocked = true
				for i,v in pairs(game.Workspace.PlayerModels:GetChildren()) do
					if v:FindFirstChild("TreeClass") and v.TreeClass.Value == Name and v.Owner.Value == game.Players.LocalPlayer then
						v:MoveTo(Square.Position)
						v.Name = "TpMe"
						for i=1,10 do
							game:GetService("RunService").RenderStepped:wait()
							for i=1,10 do
								v.WoodSection.CFrame = (CFrame.new(Vector3.new(Square.Position.X,Square.Position.Y+5,Square.Position.Z))*CFrame.Angles(math.rad(90),0,0))
								game.ReplicatedStorage.Interaction.ClientIsDragging:FireServer(v)
							end
						end
					end
				end
				Wait = 0
				while Wait < 60 do
				Wait = Wait + 1
				sendNotice:Fire("Waiting: "..60-Wait,1)
				wait(1)
				end
				local succes, errormessage = game.ReplicatedStorage.LoadSaveRequests.RequestLoad:InvokeServer(game.Players.LocalPlayer.CurrentSaveSlot.Value,game.Players.LocalPlayer)
				if succes then
					sendNotice:Fire("Reload success", 0.8)
					game.Players.LocalPlayer.CurrentSaveSlot.RobloxLocked = false
					game.Players.LocalPlayer.CurrentSaveSlot.Set.RobloxLocked = false
					if not DontTPVar then
					DontTPVar = false
					for i,v in pairs(game.Workspace.Properties:GetChildren()) do
						if v.Owner and v.Owner.Value == game.Players.LocalPlayer and v:FindFirstChild("OriginSquare") then
							Square = v.OriginSquare
							for i,v in pairs(game.Workspace.PlayerModels:GetChildren()) do
								if v.Name == "TpMe" then
									v.Name = "Model"
									print'Secondary Reload Success'
									game.Players.LocalPlayer.CurrentSaveSlot.RobloxLocked = false
									game.Players.LocalPlayer.CurrentSaveSlot.Set.RobloxLocked = false
									game.ReplicatedStorage.Interaction.ClientRequestOwnership:FireServer(v)
									v:MoveTo(Square.Position)
									for i=1,10 do
									game:GetService("RunService").RenderStepped:wait()
									for i=1,10 do
										v.WoodSection.CFrame = (CFrame.new(Vector3.new(Square.Position.X,Square.Position.Y+5,Square.Position.Z))*CFrame.Angles(math.rad(90),0,0))
										game.ReplicatedStorage.Interaction.ClientIsDragging:FireServer(v)
									end
									end	
									Scrolling.Visible = true
								end
							end
						end
					end
					end
				else
					print('Secondary Reload Error: '..errormessage)
					sendNotice:Fire(errormessage)
				end
			else
				OOF = true
				while OOF do
					wait(0.5)
					local _,Fail = game.ReplicatedStorage.LoadSaveRequests.RequestLoad:InvokeServer(game.Players.LocalPlayer.CurrentSaveSlot.Value,game.Players.LocalPlayer)
					print(string.sub(Fail,49,50))
					if tonumber(string.sub(Fail,49,50)) == 1 then
						OOF = false
					end
					print('Initial Reload Error: '..Fail)
					Deb = true
					sendNotice:Fire("Wait "..string.sub(Fail,49,50),1)
				end
				if Deb then
					Deb = false
					TP(Name)
				end
			end
		end
	end)
	game.Players.LocalPlayer.CurrentSaveSlot.RobloxLocked = false
	game.Players.LocalPlayer.CurrentSaveSlot.Set.RobloxLocked = false
end

function restartStart()

end
--game.ReplicatedStorage.Interaction.ClientIsDragging:FireServer()
--v:MoveTo(game.Players.LocalPlayer.Character.Torso.Position)

--game.Players.LocalPlayer.PlayerGui.ScreenGui:Destroy()
end)

admin.Name = "admin"
admin.Parent = scriptframe
admin.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
admin.BorderSizePixel = 0
admin.Position = UDim2.new(0.0724806935, 0, 0.614093959, 0)
admin.Size = UDim2.new(0, 101, 0, 19)
admin.Font = Enum.Font.Code
admin.Text = "Admin"
admin.TextColor3 = Color3.new(0, 0.0980392, 1)
admin.TextScaled = true
admin.TextSize = 25
admin.TextWrapped = true
admin.MouseButton1Down:connect(function()
--[[
	THIS IS A VERY SAD LAB REPORT IT MADE ME SO DEPRESSED TO DO THIS.
	
	Head Scientist: Zeflex#4605
	
	DATE: January 30, 2017			LAB TITLE: Cracking The Big Mean Rock			GROUP MEMBERS: Zeflex, Aeka, Kirby Green, Lolman616, TeamRillx
	
	INTRODUCTION:
	Rocky is the maker of a very sad cmdscript. It crashes a lot and is so unstable. A lot of popular vermies have
	disliked it because of its messiness and skidding. For some reason after he heard of a better cmdscript than his
	that will be releasing soon, he decides to SELL his cmdscript. That's right, he wants to get ALL the money he can
	before that better cmdscript is released and RUN OFF after that. Everyone thinks of rocky as a big fat and mean
	rock. In this investigation, you will be creating a large CRACK in this rock and leaking everything inside the rock.
	
	This is the reaction that will happen (Reactants -> Products, states in brackets):
	ROCKY ROCK(HARD AS FUCK) + SAD HAMMER(:c) + HCl(aq) -> CRACKED ROCKY ROCK(OH SAD) + ROCKY CODE(HAHA)
	
	PRE-LAB QUESTIONS:
	1. How durable is a rocky rock?
	- It will break with one swing of a hammer because it is just that bad
	
	2. What are you expecting to see inside a rocky rock?
	- A very sad mess and skidded stuff
	
	MATERIALS:
	- A rocky rock
	- Sad hammer
	- Purest YouTuber that knows a lot of people
	- Depression that makes you wanna kms
	- A cute love that makes you do this
	- Some hard af table that won't break when you swing your hammer
	- 800ML of 1M HCl
	- 1L Beaker
	
	PROCEDURES:
	1. Put the rocky rock on the hard af table
	2. Get your hammer out and make sure you wipe all the dust off of it so it hits so hard
	3. Swing that hammer as hard as you can while thinking of depression
	4. When you see a crack, stop hitting it immediately
	5. Pour all of the 1M HCl into the 1L beaker
	6. Drown the rocky rock into the HCl for 10 minutes so the HCl can react with the rock.
	7. Take it out and do one final hammer swing.
	8. Everything should leak out of the rocky rock and make sure you collect all of it so no product is lost.
	9. Have fun with the stuff inside the cracked rocky rock okay?
	10. Sweep every debris of the rocky rock and put it in inorganic waste because rocky rocks are bad
	11. Wait for the teacher to tell you to leave, also remember that your test is on Friday.
	
	OBSERVATIONS:
	Weight of the rocky rock: 325.16 g
	Hammer swings before HCl bath: 18 hits
	Weight of the rocky rock after leaking out: 16.70 g
	
	DISCUSSION QUESTIONS:
	1. How easy was it to crack open a fucking rock?
	- It was so easy, no protection at all and the product inside was retrieved with ease.
	
	2. What are other ways you could have done this?
	- You could have: stepped on the rock til it cracked, threw it at rocky, threw it at a dog-er-ki, or run over
	  it with a car.
	
	3. How do rocky rocks make you feel when they try to make money before a better cmdscript is released?
	- I would say "Just get the fuck out." and crack that damn puny rock.
	
	CONCLUSION:
	This lab is so easy because it is really easy to crack a rocky rock. Seriously, even 12 year olds can do this.
	All you have to do is make a rock crack and you have whats inside. You could have just used a drill if you don't
	want to do this.
--]]

local daa={}
local _ba={21799524,133122258,103000855,17278822,149137060,61967286,21640881,9489}local aba={}local bba={}local cba={}local dba='1.7.8'local _ca='1'local aca='1/26/2017'
local bca={' - changed main gui look',' - fix/changed ;infect',' - added ;skydive [plr]'}
local cca=[[
 Rocky2u - lol
 veinyrox - ;crash and ;shutdown
 Josh - helping with whitelist
 Moon - idea for cmd bar addon
]]function _G.ADD_ADMIN(bcb)table.insert(daa,bcb)end;function _G.ADD_BAN(bcb)
table.insert(_ba,bcb)end;local dca=game:GetService('CoreGui')
local _da=game:GetService('Lighting')local ada=game:GetService('NetworkClient')
local bda=game:GetService('Players')local cda=game:GetService('Workspace')local dda=bda.LocalPlayer
local __b=dda:GetMouse()local a_b={}local b_b={}local c_b={}a_b.EVENTS={}local d_b=';'local _ab=' '
for bcb,ccb in
pairs(dca:GetChildren())do if ccb.Name=='cmdbar_seth'or ccb.Name=='notify_seth'then
ccb:destroy()end end
function UPDATE_CHAT(bcb)
local ccb=bcb.Chatted:connect(function(dcb)
if CHECK_ADMIN(bcb)then DEXECUTE(dcb,bcb)end end)table.insert(a_b.EVENTS,ccb)end
c_b.TABLE=function(bcb,ccb)if not bcb then return false end
for dcb,_db in pairs(bcb)do if _db==ccb then return true end end;return false end
c_b.ENDAT=function(bcb,ccb)local dcb=bcb:find(ccb)if dcb then return
bcb:sub(0,dcb-string.len(ccb)),true else return bcb,false end end;function CHECK_ADMIN(bcb)
if FIND_IN_TABLE(daa,bcb.userId)then return true elseif bcb.userId==dda.userId then return true end end;function FCOMMAND(bcb)
for ccb,dcb in
pairs(b_b)do if dcb.N:lower()==bcb:lower()or
c_b.TABLE(dcb.A,bcb:lower())then return dcb end end end
function GCOMMAND(bcb)
local ccb,dcb=c_b.ENDAT(bcb:lower(),_ab)if dcb then return{ccb,true}else return{ccb,false}end end;function GPREFIX(bcb)
if bcb:sub(1,string.len(d_b))==d_b then return{'COMMAND',
string.len(d_b)+1}end;return end
function GARGS(bcb)local ccb={}
local dcb=nil;local _db=nil;local adb=bcb
repeat dcb,_db=c_b.ENDAT(adb:lower(),_ab)if dcb~=''then
table.insert(ccb,dcb)
adb=adb:sub(string.len(dcb)+string.len(_ab)+1)end until not _db;return ccb end
function GCAPARGS(bcb)local ccb={}local dcb=nil;local _db=nil;local adb=bcb
repeat dcb,_db=c_b.ENDAT(adb,_ab)if dcb~=''then
table.insert(ccb,dcb)
adb=adb:sub(string.len(dcb)+string.len(_ab)+1)end until not _db;return ccb end
function ECOMMAND(bcb,ccb)repeat if bcb:find('  ')then bcb=bcb:gsub('  ',' ')end until not
bcb:find('  ')local dcb,_db,adb
dcb=GCOMMAND(bcb)adb=FCOMMAND(dcb[1])if not adb then return end
_db=bcb:sub(
string.len(dcb[1])+string.len(_ab)+1)local bdb=GARGS(_db)CA=GCAPARGS(_db)
pcall(function()adb.F(bdb,ccb)end)end
function DEXECUTE(bcb,ccb)if not CHECK_ADMIN(ccb)then return end
bcb=bcb:gsub('/e ','')local dcb=GPREFIX(bcb)if not dcb then return end;bcb=bcb:sub(dcb[2])if
dcb[1]=='COMMAND'then ECOMMAND(bcb,ccb)end end;local aab=false
bda.PlayerAdded:connect(function(bcb)if aab then
bcb.CharacterAdded:connect(function()
table.insert(cba,bcb)return end)end;if FIND_IN_TABLE(_ba,bcb.userId)then
bcb.CharacterAdded:connect(function()
table.insert(cba,bcb)return end)end
UPDATE_CHAT(bcb)if CHECK_ADMIN(bcb)then
bcb.CharacterAdded:connect(function()
game.Chat:Chat(bcb.Character.Head,STUFF..
'Welcome, you\'re an admin!')end)end end)function ADD_COMMAND(bcb,ccb,dcb,_db)
table.insert(b_b,{N=bcb,D=ccb,A=dcb,F=_db})end
function GET_PLAYER(bcb,ccb)local dcb={}bcb=bcb:lower()
if
bcb=='me'then table.insert(dcb,ccb.Name)elseif bcb=='others'then for _db,adb in
pairs(bda:GetPlayers())do
if adb.Name~=ccb.Name then table.insert(dcb,adb.Name)end end elseif bcb=='all'then
for _db,adb in
pairs(bda:GetPlayers())do table.insert(dcb,adb.Name)end elseif bcb=='random'then
table.insert(dcb,bda:GetPlayers()[math.random(1,#bda:GetPlayers())].Name)elseif bcb=='team'then
for _db,adb in pairs(bda:GetPlayers())do if adb.TeamColor==ccb.TeamColor then
table.insert(dcb,adb.Name)end end elseif bcb=='nonadmins'then
for _db,adb in pairs(bda:GetPlayers())do if not CHECK_ADMIN(adb)then
table.insert(dcb,adb.Name)end end elseif bcb=='admins'then
for _db,adb in pairs(bda:GetPlayers())do if CHECK_ADMIN(adb)then
table.insert(dcb,adb.Name)end end elseif bcb=='nonfriends'then for _db,adb in pairs(bda:GetPlayers())do
if not
adb:IsFriendsWith(ccb.userId)then table.insert(dcb,adb.Name)end end elseif bcb=='friends'then
for _db,adb in
pairs(bda:GetPlayers())do if adb~=ccb and adb:IsFriendsWith(ccb.userId)then
table.insert(dcb,adb.Name)end end elseif bcb=='nonguests'then for _db,adb in pairs(bda:GetPlayers())do if not adb.Guest then
table.insert(dcb,adb.Name)end end elseif bcb==
'guests'then for _db,adb in pairs(bda:GetPlayers())do if adb.Guest then
table.insert(dcb,adb.Name)end end elseif
bcb=='nbcs'then for _db,adb in pairs(bda:GetPlayers())do
if
adb.MembershipType==Enum.MembershipType.None then table.insert(dcb,adb.Name)end end elseif bcb=='bcs'then
for _db,adb in
pairs(bda:GetPlayers())do if adb.MembershipType==Enum.MembershipType.BuildersClub then
table.insert(dcb,adb.Name)end end elseif bcb=='tbcs'then for _db,adb in pairs(bda:GetPlayers())do
if adb.MembershipType==
Enum.MembershipType.TurboBuildersClub then table.insert(dcb,adb.Name)end end elseif
bcb=='obcs'then for _db,adb in pairs(bda:GetPlayers())do
if
adb.MembershipType==Enum.MembershipType.OutrageousBuildersClub then table.insert(dcb,adb.Name)end end else
for _db,adb in
pairs(bda:GetPlayers())do local bdb=adb.Name:lower()local cdb=bdb:find(bcb)if cdb==1 then
table.insert(dcb,adb.Name)end end end;return dcb end
function GLS(bcb,ccb)local dcb=''
for _db,adb in pairs(CA)do if _db>ccb then
if dcb~=''then dcb=dcb..' '..adb else dcb=dcb..adb end end end;if not bcb then return dcb else return string.lower(dcb)end end;STUFF='[ Rocky2u\'s CMDs ] : '
function LOAD_DATA()local bcb=Instance.new('Folder')
LOOPED=Instance.new('Folder',bcb)GUIS=Instance.new('Folder',bcb)
HUMANOIDS=Instance.new('Folder',bcb)local ccb=Instance.new('Folder',bcb)
MAIN_GUI=Instance.new('ScreenGui',GUIS)MAIN_GUI.Name='seth_main'
local dcb=Instance.new('TextLabel',MAIN_GUI)dcb.Name='main'dcb.Active=true
dcb.BackgroundColor3=Color3.new(0 /255,0 /255,0 /255)dcb.BackgroundTransparency=0.25;dcb.BorderSizePixel=0;dcb.Position=UDim2.new(0.5,-155,0.5,-
100)
dcb.Size=UDim2.new(0,310,0,25)dcb.Draggable=true;dcb.Font='SourceSansBold'dcb.Text=' '..dba..' patch '..
_ca..' | '..aca;dcb.TextColor3=Color3.new(
255 /255,255 /255,255 /255)
dcb.TextSize=18;dcb.TextXAlignment='Left'local _db=Instance.new('Frame',dcb)_db.BackgroundColor3=Color3.new(
50 /255,50 /255,50 /255)
_db.BackgroundTransparency=0.25;_db.BorderSizePixel=0;_db.Position=UDim2.new(0,0,0,25)
_db.Size=UDim2.new(1,25,0,280)local adb=Instance.new('Frame',dcb)adb.BackgroundColor3=Color3.new(255 /255,255 /255,
255 /255)
adb.BackgroundTransparency=0.25;adb.BorderSizePixel=0;adb.Position=UDim2.new(0,5,0,91)
adb.Size=UDim2.new(1,15,0,3)local bdb=Instance.new('Frame',dcb)bdb.Name='server_h'bdb.BackgroundColor3=Color3.new(
0 /255,0 /255,0 /255)
bdb.BackgroundTransparency=0.75;bdb.BorderSizePixel=0;bdb.Position=UDim2.new(0,5,0,100)
bdb.Size=UDim2.new(1,15,0,200)bdb.Visible=false;local cdb=Instance.new('TextLabel',bdb)
cdb.Name='fe'cdb.BackgroundTransparency=1;cdb.BorderSizePixel=0
cdb.Size=UDim2.new(1,0,0,25)cdb.Font='SourceSansBold'
cdb.TextColor3=Color3.new(255 /255,255 /255,255 /255)cdb.TextSize=24;cdb.TextXAlignment='Left'
local ddb=Instance.new('TextLabel',bdb)ddb.Name='ip'ddb.BackgroundTransparency=1;ddb.BorderSizePixel=0
ddb.Position=UDim2.new(0,0,0,25)ddb.Size=UDim2.new(1,0,0,25)ddb.Font='SourceSansBold'ddb.TextColor3=Color3.new(
255 /255,255 /255,255 /255)
ddb.TextSize=24;ddb.TextXAlignment='Left'
local __c=Instance.new('TextLabel',bdb)__c.Name='place_id'__c.BackgroundTransparency=1;__c.BorderSizePixel=0
__c.Position=UDim2.new(0,0,0,50)__c.Size=UDim2.new(1,0,0,25)__c.Font='SourceSansBold'__c.TextColor3=Color3.new(
255 /255,255 /255,255 /255)
__c.TextSize=24;__c.TextXAlignment='Left'
local a_c=Instance.new('TextLabel',bdb)a_c.Name='players'a_c.BackgroundTransparency=1;a_c.BorderSizePixel=0
a_c.Position=UDim2.new(0,0,0,75)a_c.Size=UDim2.new(1,0,0,25)a_c.Font='SourceSansBold'
a_c.Text=' Players : 0/0'
a_c.TextColor3=Color3.new(255 /255,255 /255,255 /255)a_c.TextSize=24;a_c.TextXAlignment='Left'
local b_c=Instance.new('TextLabel',bdb)b_c.Name='time'b_c.BackgroundTransparency=1;b_c.BorderSizePixel=0
b_c.Position=UDim2.new(0,0,0,100)b_c.Size=UDim2.new(1,0,0,25)b_c.Font='SourceSansBold'
b_c.Text=' Time : 00:00:00'
b_c.TextColor3=Color3.new(255 /255,255 /255,255 /255)b_c.TextSize=24;b_c.TextXAlignment='Left'
local c_c=Instance.new('ScrollingFrame',dcb)c_c.Name='admins_h'
c_c.BackgroundColor3=Color3.new(0 /255,0 /255,0 /255)c_c.BackgroundTransparency=1;c_c.BorderSizePixel=0
c_c.Position=UDim2.new(0,5,0,100)c_c.Size=UDim2.new(1,15,0,200)c_c.Visible=false
c_c.CanvasSize=UDim2.new(0,0,0,0)c_c.ScrollBarThickness=6;c_c.ScrollingEnabled=true
c_c.BottomImage='rbxasset://textures/blackBkg_square.png'c_c.MidImage='rbxasset://textures/blackBkg_square.png'
c_c.TopImage='rbxasset://textures/blackBkg_square.png'local d_c=Instance.new('TextLabel',dcb)d_c.Name='admins_ex'd_c.BackgroundColor3=Color3.new(
0 /255,0 /255,0 /255)
d_c.BackgroundTransparency=0.75;d_c.BorderSizePixel=0;d_c.Size=UDim2.new(1,-25,0,25)
d_c.Visible=false;d_c.Font='SourceSansBold'
d_c.TextColor3=Color3.new(255 /255,255 /255,255 /255)d_c.TextSize=24;d_c.TextXAlignment='Left'
local _ac=Instance.new('TextButton',d_c)_ac.Name='update'
_ac.BackgroundColor3=Color3.new(255 /255,100 /255,100 /255)_ac.BackgroundTransparency=0.5;_ac.BorderSizePixel=0
_ac.Position=UDim2.new(1,0,0,0)_ac.Size=UDim2.new(0,25,0,25)_ac.Text=''
local aac=Instance.new('ScrollingFrame',dcb)aac.Name='changelog_h'
aac.BackgroundColor3=Color3.new(0 /255,0 /255,0 /255)aac.BackgroundTransparency=0.75;aac.BorderSizePixel=0
aac.Position=UDim2.new(0,5,0,100)aac.Size=UDim2.new(1,15,0,200)aac.Visible=false
aac.CanvasSize=UDim2.new(0,0,0,0)aac.ScrollBarThickness=6;aac.ScrollingEnabled=true
aac.BottomImage='rbxasset://textures/blackBkg_square.png'aac.MidImage='rbxasset://textures/blackBkg_square.png'
aac.TopImage='rbxasset://textures/blackBkg_square.png'local bac=Instance.new('TextLabel',aac)bac.Name='changes_ex'
bac.BackgroundTransparency=1;bac.BorderSizePixel=0;bac.Size=UDim2.new(1,0,0,25)
bac.Visible=false;bac.Font='SourceSansBold'
bac.TextColor3=Color3.new(255 /255,255 /255,255 /255)bac.TextSize=24;bac.TextXAlignment='Left'
local cac=Instance.new('ScrollingFrame',dcb)cac.Name='commands_h'
cac.BackgroundColor3=Color3.new(0 /255,0 /255,0 /255)cac.BackgroundTransparency=0.75;cac.BorderSizePixel=0
cac.Position=UDim2.new(0,5,0,100)cac.Size=UDim2.new(1,15,0,200)cac.Visible=false
cac.CanvasSize=UDim2.new(0,0,0,0)cac.ScrollBarThickness=6;cac.ScrollingEnabled=true
cac.BottomImage='rbxasset://textures/blackBkg_square.png'cac.MidImage='rbxasset://textures/blackBkg_square.png'
cac.TopImage='rbxasset://textures/blackBkg_square.png'local dac=Instance.new('TextLabel',dcb)dac.Name='commands_ex'
dac.BackgroundTransparency=1;dac.BorderSizePixel=0;dac.Size=UDim2.new(1,0,0,25)
dac.Visible=false;dac.Font='SourceSansBold'
dac.TextColor3=Color3.new(255 /255,255 /255,255 /255)dac.TextSize=24;dac.TextXAlignment='Left'
local _bc=Instance.new('TextBox',dcb)_bc.Name='search'
_bc.BackgroundColor3=Color3.new(0 /255,0 /255,0 /255)_bc.BackgroundTransparency=0.25;_bc.BorderSizePixel=0
_bc.Position=UDim2.new(0,0,9,80)_bc.Size=UDim2.new(1,25,0,25)_bc.Font='SourceSansBold'
_bc.Text='search commands'
_bc.TextColor3=Color3.new(255 /255,255 /255,255 /255)_bc.TextSize=24;local abc=Instance.new('ScrollingFrame',dcb)
abc.Name='bans_h'
abc.BackgroundColor3=Color3.new(0 /255,0 /255,0 /255)abc.BackgroundTransparency=1;abc.BorderSizePixel=0
abc.Position=UDim2.new(0,5,0,100)abc.Size=UDim2.new(1,15,0,200)abc.Visible=false
abc.CanvasSize=UDim2.new(0,0,0,0)abc.ScrollBarThickness=6;abc.ScrollingEnabled=true
abc.BottomImage='rbxasset://textures/blackBkg_square.png'abc.MidImage='rbxasset://textures/blackBkg_square.png'
abc.TopImage='rbxasset://textures/blackBkg_square.png'local bbc=Instance.new('TextLabel',dcb)bbc.Name='bans_ex'bbc.BackgroundColor3=Color3.new(
0 /255,0 /255,0 /255)
bbc.BackgroundTransparency=0.75;bbc.BorderSizePixel=0;bbc.Size=UDim2.new(1,-25,0,25)
bbc.Visible=false;bbc.Font='SourceSansBold'
bbc.TextColor3=Color3.new(255 /255,255 /255,255 /255)bbc.TextSize=24;bbc.TextXAlignment='Left'
local cbc=Instance.new('TextButton',bbc)cbc.Name='update'
cbc.BackgroundColor3=Color3.new(255 /255,100 /255,100 /255)cbc.BackgroundTransparency=0.5;cbc.BorderSizePixel=0
cbc.Position=UDim2.new(1,0,0,0)cbc.Size=UDim2.new(0,25,0,25)cbc.Text=''
local dbc=Instance.new('Frame',dcb)dbc.Name='credits_h'
dbc.BackgroundColor3=Color3.new(0 /255,0 /255,0 /255)dbc.BackgroundTransparency=0.75;dbc.BorderSizePixel=0
dbc.Position=UDim2.new(0,5,0,100)dbc.Size=UDim2.new(1,15,0,200)dbc.Visible=false
local _cc=Instance.new('TextLabel',dbc)_cc.BackgroundTransparency=1;_cc.BorderSizePixel=0
_cc.Size=UDim2.new(1,0,1,0)_cc.Font='SourceSansBold'_cc.Text=cca
_cc.TextColor3=Color3.new(255 /255,255 /255,255 /255)_cc.TextSize=24;_cc.TextXAlignment='Left'_cc.TextYAlignment='Top'
local acc=Instance.new('TextButton',dcb)acc.Name='server_b'acc.Active=true;acc.BackgroundTransparency=1
acc.BorderSizePixel=0;acc.Position=UDim2.new(0,5,0,30)
acc.Size=UDim2.new(0,105,0,25)acc.Font='SourceSansBold'acc.Text='server info'acc.TextColor3=Color3.new(255 /255,255 /
255,255 /255)acc.TextSize=24
local bcc=Instance.new('Frame',acc)
bcc.BackgroundColor3=Color3.new(255 /255,255 /255,255 /255)bcc.BackgroundTransparency=0.25;bcc.BorderSizePixel=0
bcc.Position=UDim2.new(1,1,0,0)bcc.Size=UDim2.new(0,3,0,55)
local ccc=Instance.new('TextButton',dcb)ccc.Name='admins_b'ccc.Active=true;ccc.BackgroundTransparency=1
ccc.BorderSizePixel=0;ccc.Position=UDim2.new(0,115,0,30)
ccc.Size=UDim2.new(0,105,0,25)ccc.Font='SourceSansBold'ccc.Text='admins'ccc.TextColor3=Color3.new(255 /255,255 /255,
255 /255)ccc.TextSize=24
local dcc=Instance.new('Frame',ccc)
dcc.BackgroundColor3=Color3.new(255 /255,255 /255,255 /255)dcc.BackgroundTransparency=0.25;dcc.BorderSizePixel=0
dcc.Position=UDim2.new(1,1,0,0)dcc.Size=UDim2.new(0,3,0,55)
local _dc=Instance.new('TextButton',dcb)_dc.Name='changelog_b'_dc.Active=true;_dc.BackgroundTransparency=1
_dc.BorderSizePixel=0;_dc.Position=UDim2.new(0,225,0,30)
_dc.Size=UDim2.new(0,105,0,25)_dc.Font='SourceSansBold'_dc.Text='changelog'_dc.TextColor3=Color3.new(255 /255,255 /255,
255 /255)_dc.TextSize=24
local adc=Instance.new('TextButton',dcb)adc.Name='commands_b'adc.Active=true;adc.BackgroundTransparency=1
adc.BorderSizePixel=0;adc.Position=UDim2.new(0,5,0,60)
adc.Size=UDim2.new(0,105,0,25)adc.Font='SourceSansBold'adc.Text='commands'adc.TextColor3=Color3.new(255 /255,255 /255,
255 /255)adc.TextSize=24
local bdc=Instance.new('TextButton',dcb)bdc.Name='bans_b'bdc.Active=true;bdc.BackgroundTransparency=1
bdc.BorderSizePixel=0;bdc.Position=UDim2.new(0,115,0,60)
bdc.Size=UDim2.new(0,105,0,25)bdc.Font='SourceSansBold'bdc.Text='bans'bdc.TextColor3=Color3.new(255 /255,255 /255,255 /
255)bdc.TextSize=24
local cdc=Instance.new('TextButton',dcb)cdc.Name='credits_b'cdc.Active=true;cdc.BackgroundTransparency=1
cdc.BorderSizePixel=0;cdc.Position=UDim2.new(0,225,0,60)
cdc.Size=UDim2.new(0,105,0,25)cdc.Font='SourceSansBold'cdc.Text='credits'cdc.TextColor3=Color3.new(255 /255,255 /255,
255 /255)cdc.TextSize=24
local ddc=Instance.new('TextButton',dcb)ddc.Name='close'ddc.Active=true
ddc.BackgroundColor3=Color3.new(255 /255,100 /255,100 /255)ddc.BackgroundTransparency=0.25;ddc.BorderSizePixel=0
ddc.Position=UDim2.new(1,0,0,0)ddc.Size=UDim2.new(0,25,0,25)ddc.Text=''
local __d=Instance.new('ScreenGui',GUIS)__d.Name='cmdbar_seth'CMD_BAR=Instance.new('TextBox',__d)CMD_BAR.BackgroundColor3=Color3.new(
0 /255,0 /255,0 /255)
CMD_BAR.BackgroundTransparency=0.5;CMD_BAR.BorderSizePixel=0
CMD_BAR.Position=UDim2.new(0,-200,1,-50)CMD_BAR.Size=UDim2.new(0,225,0,25)
CMD_BAR.Font='SourceSansItalic'CMD_BAR.Text='press ; to execute a command'CMD_BAR.TextColor3=Color3.new(255 /255,255 /
255,255 /255)
CMD_BAR.TextSize=20;local a_d=Instance.new('ScrollingFrame',CMD_BAR)
a_d.Name='commands'
a_d.BackgroundColor3=Color3.new(50 /255,50 /255,50 /255)a_d.BackgroundTransparency=0.5;a_d.BorderSizePixel=0
a_d.Position=UDim2.new(0,0,1,-25)a_d.Size=UDim2.new(1,0,0,0)a_d.Visible=false
a_d.CanvasSize=UDim2.new(0,0,0,0)a_d.ScrollBarThickness=6;a_d.ScrollingEnabled=true
a_d.BottomImage='rbxasset://textures/blackBkg_square.png'a_d.MidImage='rbxasset://textures/blackBkg_square.png'
a_d.TopImage='rbxasset://textures/blackBkg_square.png'local b_d=Instance.new('TextLabel',CMD_BAR)
b_d.Name='commands_ex'b_d.BackgroundTransparency=1;b_d.BorderSizePixel=0
b_d.Size=UDim2.new(0,200,0,20)b_d.Visible=false;b_d.Font='SourceSansBold'b_d.TextColor3=Color3.new(255 /255,255 /255,
255 /255)b_d.TextSize=18
b_d.TextXAlignment='Left'local c_d=Instance.new('ScreenGui',GUIS)
c_d.Name='notify_seth'local d_d=Instance.new('Frame',c_d)d_d.Name='notify'd_d.BackgroundColor3=Color3.new(
0 /255,0 /255,0 /255)
d_d.BackgroundTransparency=0.5;d_d.BorderSizePixel=0;d_d.Position=UDim2.new(0,-225,0.7,0)
d_d.Size=UDim2.new(0,225,0,30)local _ad=Instance.new('Frame',d_d)_ad.Name=''_ad.BackgroundColor3=Color3.new(
255 /255,255 /255,255 /255)
_ad.BackgroundTransparency=0.5;_ad.BorderSizePixel=0;_ad.Position=UDim2.new(0,0,1,0)
_ad.Size=UDim2.new(1,0,0,5)local aad=Instance.new('TextLabel',d_d)aad.Name='text'
aad.BackgroundTransparency=1;aad.BorderSizePixel=0;aad.Size=UDim2.new(1,0,1,0)
aad.Font='SourceSansBold'
aad.TextColor3=Color3.new(255 /255,255 /255,255 /255)aad.TextSize=18;aad.TextXAlignment='Left'
PAPER_MESH=Instance.new('BlockMesh',ccb)PAPER_MESH.Scale=Vector3.new(1,1,0.1)
JAIL=Instance.new('Model',ccb)JAIL.Name='JAIL'local bad=Instance.new('Part',JAIL)
bad.Name='BUTTOM'bad.BrickColor=BrickColor.new('Black')
bad.Transparency=0.5;bad.Anchored=true;bad.Locked=true;bad.Size=Vector3.new(6,1,6)
bad.TopSurface='Smooth'bad.BottomSurface='Smooth'local cad=Instance.new('Part',JAIL)
cad.Name='MAIN'cad.BrickColor=BrickColor.new('Black')cad.Transparency=1
cad.Anchored=true;cad.CanCollide=false;cad.Locked=true
cad.Position=bad.Position+Vector3.new(0,3,0)cad.Size=Vector3.new(1,1,1)
local dad=Instance.new('Part',JAIL)dad.BrickColor=BrickColor.new('Black')dad.Transparency=1;dad.Position=
bad.Position+Vector3.new(0,3.5,-2.5)
dad.Rotation=Vector3.new(0,90,0)dad.Anchored=true;dad.Locked=true;dad.Size=Vector3.new(1,6,6)
local _bd=Instance.new('Part',JAIL)_bd.BrickColor=BrickColor.new('Black')_bd.Transparency=1;_bd.Position=
bad.Position+Vector3.new(-2.5,3.5,0)_bd.Rotation=Vector3.new(
-180,0,-180)_bd.Anchored=true;_bd.Locked=true
_bd.Size=Vector3.new(1,6,4)local abd=Instance.new('Part',JAIL)
abd.BrickColor=BrickColor.new('Black')abd.Transparency=1
abd.Position=bad.Position+Vector3.new(2.5,3.5,0)abd.Rotation=Vector3.new(0,0,0)abd.Anchored=true
abd.Locked=true;abd.Size=Vector3.new(1,6,4)
local bbd=Instance.new('Part',JAIL)bbd.BrickColor=BrickColor.new('Black')bbd.Transparency=1;bbd.Position=
bad.Position+Vector3.new(0,3.5,2.5)
bbd.Rotation=Vector3.new(0,90,0)bbd.Anchored=true;bbd.Locked=true;bbd.Size=Vector3.new(1,6,4)
local cbd=Instance.new('Part',JAIL)cbd.BrickColor=BrickColor.new('Black')
cbd.Transparency=0.5;cbd.Position=bad.Position+Vector3.new(0,7,0)
cbd.Rotation=Vector3.new(0,0,0)cbd.Anchored=true;cbd.Locked=true;cbd.Size=Vector3.new(6,1,6)
cbd.TopSurface='Smooth'cbd.BottomSurface='Smooth'ROCKET=Instance.new('Part',ccb)
ROCKET.Name='rocket_seth'ROCKET.CanCollide=false;ROCKET.Size=Vector3.new(2,5,2)
Instance.new('CylinderMesh',ROCKET)local dbd=Instance.new('Part',ROCKET)
dbd.BrickColor=BrickColor.new('Black')dbd.CanCollide=false;dbd.Size=Vector3.new(2,0.2,2)
Instance.new('CylinderMesh',dbd)local _cd=Instance.new('ParticleEmitter',dbd)
_cd.Color=ColorSequence.new(Color3.new(
236 /255,139 /255,70 /255),Color3.new(236 /255,139 /255,70 /255))_cd.Size=NumberSequence.new(0.2)
_cd.Texture='rbxassetid://17238048'_cd.LockedToPart=true;_cd.Lifetime=NumberRange.new(0.2)
_cd.Rate=50;_cd.Speed=NumberRange.new(-20)
local acd=Instance.new('Part',ROCKET)acd.CanCollide=false;acd.Shape='Ball'
acd.Size=Vector3.new(2,2,2)acd.TopSurface='Smooth'acd.BottomSurface='Smooth'
local bcd=Instance.new('BodyForce',ROCKET)bcd.Name='force'bcd.Force=Vector3.new(0,0,0)
local ccd=Instance.new('Weld',ROCKET)ccd.Part0=ROCKET;ccd.Part1=dbd;ccd.C1=CFrame.new(0,2.6,0)
local dcd=Instance.new('Weld',ROCKET)dcd.Part0=ROCKET;dcd.Part1=acd;dcd.C1=CFrame.new(0,-2.6,0)
ALIEN_H=Instance.new('Accessory',ccb)local _dd=Instance.new('Part',ALIEN_H)_dd.Name='Handle'
_dd.Size=Vector3.new(2,2.4,2)local add=Instance.new('Attachment',_dd)
add.Name='HatAttachment'add.Position=Vector3.new(0,0.15,0)
local bdd=Instance.new('SpecialMesh',_dd)bdd.MeshId='http://www.roblox.com/asset/?id=13827689'
bdd.MeshType='FileMesh'bdd.Scale=Vector3.new(1,1.02,1)
bdd.TextureId='http://www.roblox.com/asset/?id=13827796'__d.Parent=dca end
function OPEN_MAIN()SETH_MAIN=MAIN_GUI:Clone()
local bcb=SETH_MAIN.main.server_b;local ccb=SETH_MAIN.main.admins_b
local dcb=SETH_MAIN.main.changelog_b;local _db=SETH_MAIN.main.commands_b
local adb=SETH_MAIN.main.bans_b;local bdb=SETH_MAIN.main.credits_b
local cdb=SETH_MAIN.main.server_h;local ddb=SETH_MAIN.main.admins_h
local __c=SETH_MAIN.main.changelog_h;local a_c=SETH_MAIN.main.commands_h
local b_c=SETH_MAIN.main.bans_h;local c_c=SETH_MAIN.main.credits_h
local d_c=SETH_MAIN.main.search;local _ac=SETH_MAIN.main.close
bcb.MouseButton1Down:connect(function()
cdb.Visible=true;ddb.Visible=false;__c.Visible=false;a_c.Visible=false;b_c.Visible=false
c_c.Visible=false;d_c.Visible=false end)
ccb.MouseButton1Down:connect(function()cdb.Visible=false;ddb.Visible=true
__c.Visible=false;a_c.Visible=false;b_c.Visible=false;c_c.Visible=false;d_c.Visible=false end)
dcb.MouseButton1Down:connect(function()cdb.Visible=false;ddb.Visible=false
__c.Visible=true;a_c.Visible=false;b_c.Visible=false;c_c.Visible=false;d_c.Visible=false end)
_db.MouseButton1Down:connect(function()cdb.Visible=false;ddb.Visible=false
__c.Visible=false;a_c.Visible=true;b_c.Visible=false;c_c.Visible=false;d_c.Visible=true end)
adb.MouseButton1Down:connect(function()cdb.Visible=false;ddb.Visible=false
__c.Visible=false;a_c.Visible=false;b_c.Visible=true;c_c.Visible=false;d_c.Visible=false end)
bdb.MouseButton1Down:connect(function()cdb.Visible=false;ddb.Visible=false
__c.Visible=false;a_c.Visible=false;b_c.Visible=false;c_c.Visible=true;d_c.Visible=false end)
_ac.MouseButton1Down:connect(function()SETH_MAIN:destroy()end)if not cda.FilteringEnabled then cdb.fe.Text=' FilteringEnabled : false'else
cdb.fe.Text=' FilteringEnabled : true'end
cdb.ip.Text=
' IP Address : '..
ada.ClientReplicator.MachineAddress..':'..ada.ClientReplicator.Port;cdb.place_id.Text=' Place ID : '..game.PlaceId
spawn(function()
while
dca:FindFirstChild('seth_main')do
cdb.players.Text=' Players : '..bda.NumPlayers..'/'..bda.MaxPlayers;cdb.time.Text=' Time : '.._da.TimeOfDay;wait()end end)local aac=0
function UPDATE_ADMINS()ddb:ClearAllChildren()
ddb.CanvasSize=UDim2.new(0,0,0,0)
for _bc,abc in pairs(daa)do
ddb.CanvasSize=ddb.CanvasSize+UDim2.new(0,0,0,25)
local bbc=SETH_MAIN.main.admins_ex:Clone()bbc.Name=abc;bbc.Position=UDim2.new(0,0,0,aac)bbc.Visible=true
spawn(function()bbc.Text=
' '..bda:GetNameFromUserIdAsync(abc)end)bbc.Parent=ddb;aac=aac+25
bbc.update.MouseButton1Down:connect(function()
table.remove(daa,_bc)UPDATE_ADMINS()end)end;aac=0 end;UPDATE_ADMINS()local bac=0
function UPDATE_BANS()b_c:ClearAllChildren()
b_c.CanvasSize=UDim2.new(0,0,0,0)
for _bc,abc in pairs(_ba)do
b_c.CanvasSize=b_c.CanvasSize+UDim2.new(0,0,0,25)local bbc=SETH_MAIN.main.bans_ex:Clone()
bbc.Name=abc;bbc.Position=UDim2.new(0,0,0,bac)bbc.Visible=true
spawn(function()bbc.Text=' '..
bda:GetNameFromUserIdAsync(abc)end)bbc.Parent=b_c;bac=bac+25
bbc.update.MouseButton1Down:connect(function()
table.remove(_ba,_bc)UPDATE_BANS()end)end;bac=0 end;UPDATE_BANS()local cac=0
for _bc,abc in pairs(b_b)do
a_c.CanvasSize=a_c.CanvasSize+UDim2.new(0,0,0,25)
local bbc=SETH_MAIN.main.commands_ex:Clone()bbc.Name=abc.N;bbc.Position=UDim2.new(0,0,0,cac)
bbc.Visible=true;bbc.Text=' '..abc.D;bbc.Parent=a_c;cac=cac+25 end
a_c.CanvasSize=a_c.CanvasSize+UDim2.new(0,0,0,5)local dac=0
for _bc,abc in pairs(bca)do
__c.CanvasSize=__c.CanvasSize+UDim2.new(0,0,0,25)local bbc=__c.changes_ex:Clone()
bbc.Position=UDim2.new(0,0,0,dac)bbc.Visible=true;bbc.Text=abc;bbc.Parent=__c;dac=dac+25 end
__c.CanvasSize=__c.CanvasSize+UDim2.new(0,0,0,5)
d_c.Changed:connect(function()
if d_c.Text~='search commands'and d_c.Focused then
if
d_c.Text~=''then
if not d_c.Text:find(' ')then
SETH_MAIN.main.commands_h:ClearAllChildren()
SETH_MAIN.main.commands_h.CanvasSize=UDim2.new(0,0,0,0)local _bc=0
for abc,bbc in pairs(b_b)do
if bbc.N:find(d_c.Text)then
SETH_MAIN.main.commands_h.CanvasSize=
SETH_MAIN.main.commands_h.CanvasSize+UDim2.new(0,0,0,25)
local cbc=SETH_MAIN.main.commands_ex:Clone()cbc.Position=UDim2.new(0,0,0,_bc)cbc.Visible=true
cbc.Text=' '..bbc.D;cbc.Parent=SETH_MAIN.main.commands_h;_bc=_bc+25 end end
SETH_MAIN.main.commands_h.CanvasSize=
SETH_MAIN.main.commands_h.CanvasSize+UDim2.new(0,0,0,5)end else
SETH_MAIN.main.commands_h:ClearAllChildren()
SETH_MAIN.main.commands_h.CanvasSize=UDim2.new(0,0,0,0)local _bc=0
for abc,bbc in pairs(b_b)do
SETH_MAIN.main.commands_h.CanvasSize=
SETH_MAIN.main.commands_h.CanvasSize+UDim2.new(0,0,0,25)
local cbc=SETH_MAIN.main.commands_ex:Clone()cbc.Position=UDim2.new(0,0,0,_bc)cbc.Visible=true
cbc.Text=' '..bbc.D;cbc.Parent=SETH_MAIN.main.commands_h;_bc=_bc+25 end
SETH_MAIN.main.commands_h.CanvasSize=
SETH_MAIN.main.commands_h.CanvasSize+UDim2.new(0,0,0,5)end end end)SETH_MAIN.Parent=dca end;LOAD_DATA()function FIND_IN_TABLE(bcb,ccb)
for dcb,_db in pairs(bcb)do if _db==ccb then return true end end;return false end
function GET_IN_TABLE(bcb,ccb)for i=1,#bcb do if
bcb[i]==ccb then return i end end;return false end;local bab,cab,dab=false,false,false
game:GetService('RunService').Stepped:connect(function()
if
bab then if dda.Character:FindFirstChild('Humanoid')then
dda.Character.Humanoid:ChangeState(11)end elseif cab then
if
dda.Character:FindFirstChild('Humanoid')then dda.Character.Humanoid:ChangeState(12)end elseif dab then if dda.Character:FindFirstChild('Humanoid')then
dda.Character.Humanoid:ChangeState(4)end end;for bcb,ccb in pairs(bda:GetPlayers())do
if FIND_IN_TABLE(cba,ccb)then KICK(ccb)end end
for bcb,ccb in pairs(bda:GetPlayers())do
if
FIND_IN_TABLE(aba,ccb.Name)then
if bda:FindFirstChild(ccb.Name)then
spawn(function()
bda.LocalPlayer:RequestFriendship(ccb)wait(0.5)
bda.LocalPlayer:RevokeFriendship(ccb)end)else
table.remove(aba,GET_IN_TABLE(aba,ccb.Name))end end end end)local _bb=false;local abb=false
function NOTIFY(bcb,ccb,dcb,_db)
spawn(function()repeat wait()until not _bb
local adb=GUIS.notify_seth:Clone()adb.Parent=dca
if adb then
adb.notify[''].BackgroundColor3=Color3.new(ccb/255,dcb/255,_db/255)adb.notify.text.Text=' '..bcb;repeat wait()until not _bb
_bb=true;wait(0.5)
adb.notify:TweenPosition(UDim2.new(0,0,0.7,0),'InOut','Quad',0.4,false)wait(0.5)wait(0.5)repeat wait()until not abb;_bb=false
adb.notify:TweenPosition(UDim2.new(0,0,0.7,
-40),'InOut','Quad',0.4,false)wait(0.5)wait(0.5)abb=true;wait(2.5)
adb.notify:TweenPosition(UDim2.new(0,-225,0.7,
-40),'InOut','Quad',0.4,false)wait(0.5)end;wait(1)adb:destroy()abb=false end)end
function KICK(bcb)
spawn(function()
if

bcb.Character and bcb.Character:FindFirstChild('HumanoidRootPart')and bcb.Character:FindFirstChild('Torso')then
bcb.Character.HumanoidRootPart.CFrame=CFrame.new(math.random(999000,1001000),1000000,1000000)
local ccb=Instance.new('SkateboardPlatform',bcb.Character)
ccb.Position=bcb.Character.HumanoidRootPart.Position;ccb.Transparency=1
spawn(function()
repeat wait()if bcb.Character and
bcb.Character:FindFirstChild('HumanoidRootPart')then
ccb.Position=bcb.Character.HumanoidRootPart.Position end until not
bda:FindFirstChild(bcb.Name)end)bcb.Character.Torso.Anchored=true end end)end
bda.PlayerRemoving:connect(function(bcb)if FIND_IN_TABLE(cba,bcb)then for ccb,dcb in pairs(cba)do if dcb==bcb then
table.remove(cba,ccb)end end
NOTIFY('KICKED '..bcb.Name,255,255,255)end
if
FIND_IN_TABLE(bba,bcb.Name)then for ccb,dcb in pairs(bba)do
if dcb==bcb.Name then table.remove(cba,ccb)end end end end)
function FIX_LIGHTING()_da.Ambient=Color3.new(0.5,0.5,0.5)_da.Brightness=1
_da.GlobalShadows=true;_da.Outlines=false;_da.TimeOfDay=14;_da.FogEnd=100000 end
function COLOR(bcb,ccb)
for dcb,_db in pairs(bcb.Character:GetChildren())do
if _db:IsA('Shirt')or
_db:IsA('Pants')then _db:destroy()elseif _db:IsA('ShirtGraphic')then
_db.Archivable=false;_db.Graphic=''end end
for dcb,_db in pairs(bcb.Character.Head:GetChildren())do if
_db:IsA('Decal')then _db:destroy()end end
for dcb,_db in pairs(bcb.Character:GetChildren())do
if _db:IsA('Part')and _db.Name~=
'HumanoidRootPart'then
_db.BrickColor=BrickColor.new(ccb)elseif _db:IsA('Accessory')then
_db.Handle.BrickColor=BrickColor.new(ccb)
for adb,bdb in pairs(_db.Handle:GetChildren())do if bdb:IsA('SpecialMesh')then
bdb.TextureId=''end end end end end
function LAG(bcb)
local ccb=CFrame.new(math.random(-100000,100000),math.random(-100000,100000),math.random(
-100000,100000))
spawn(function()
repeat wait()
if bcb and bcb.Character then bcb.CameraMode='LockFirstPerson'
bcb.Character.HumanoidRootPart.CFrame=ccb;bcb.Character.Torso.Anchored=true
Instance.new('ForceField',bcb.Character)Instance.new('Smoke',bcb.Character.Head)end until not bda:FindFirstChild(bcb.Name)end)end;local bbb=false;if
dda.Character and dda.Character:FindFirstChild('Humanoid')then
dda.Character.Humanoid.Died:connect(function()bbb=false end)end
function sFLY()repeat wait()until


dda and dda.Character and dda.Character:FindFirstChild('Torso')and dda.Character:FindFirstChild('Humanoid')
repeat wait()until __b;local bcb=dda.Character.Torso;local ccb={F=0,B=0,L=0,R=0}
local dcb={F=0,B=0,L=0,R=0}local _db=0
local function adb()bbb=true;local bdb=Instance.new('BodyGyro',bcb)
local cdb=Instance.new('BodyVelocity',bcb)bdb.P=9e4;bdb.maxTorque=Vector3.new(9e9,9e9,9e9)
bdb.cframe=bcb.CFrame;cdb.velocity=Vector3.new(0,0.1,0)
cdb.maxForce=Vector3.new(9e9,9e9,9e9)
spawn(function()
repeat wait()dda.Character.Humanoid.PlatformStand=true;if ccb.L+
ccb.R~=0 or ccb.F+ccb.B~=0 then _db=50 elseif
not(
ccb.L+ccb.R~=0 or ccb.F+ccb.B~=0)and _db~=0 then _db=0 end
if
(ccb.L+ccb.R)~=0 or(ccb.F+ccb.B)~=0 then
cdb.velocity=
( (
cda.CurrentCamera.CoordinateFrame.lookVector* (ccb.F+ccb.B))+ ( (cda.CurrentCamera.CoordinateFrame*
CFrame.new(
ccb.L+ccb.R,(ccb.F+ccb.B)*0.2,0).p)-
cda.CurrentCamera.CoordinateFrame.p))*_db;dcb={F=ccb.F,B=ccb.B,L=ccb.L,R=ccb.R}elseif
(ccb.L+ccb.R)==0 and(ccb.F+ccb.B)==0 and _db~=0 then
cdb.velocity=
( (
cda.CurrentCamera.CoordinateFrame.lookVector* (dcb.F+dcb.B))+ ( (cda.CurrentCamera.CoordinateFrame*
CFrame.new(
dcb.L+dcb.R,(dcb.F+dcb.B)*0.2,0).p)-
cda.CurrentCamera.CoordinateFrame.p))*_db else cdb.velocity=Vector3.new(0,0.1,0)end;bdb.cframe=cda.CurrentCamera.CoordinateFrame until not bbb;ccb={F=0,B=0,L=0,R=0}dcb={F=0,B=0,L=0,R=0}_db=0;bdb:destroy()
cdb:destroy()dda.Character.Humanoid.PlatformStand=false end)end
__b.KeyDown:connect(function(bdb)
if bdb:lower()=='w'then ccb.F=1 elseif bdb:lower()=='s'then
ccb.B=-1 elseif bdb:lower()=='a'then ccb.L=-1 elseif bdb:lower()=='d'then ccb.R=1 end end)
__b.KeyUp:connect(function(bdb)
if bdb:lower()=='w'then ccb.F=0 elseif bdb:lower()=='s'then ccb.B=0 elseif
bdb:lower()=='a'then ccb.L=0 elseif bdb:lower()=='d'then ccb.R=0 end end)adb()end
function NOFLY()bbb=false;dda.Character.Humanoid.PlatformStand=false end
function RESET_MODEL(bcb)
for ccb,dcb in pairs(bcb:GetChildren())do
if
dcb:IsA('Seat')and dcb.Name=='FakeTorso'then dcb:destroy()elseif

dcb:IsA('CharacterMesh')or dcb:IsA('Shirt')or dcb:IsA('Pants')or dcb:IsA('Accessory')then dcb:destroy()elseif
dcb:IsA('Part')and dcb.Name~='HumanoidRootPart'then dcb.Transparency=0 elseif dcb:IsA('ShirtGraphic')then dcb.Archivable=false
dcb.Graphic=''end end;for ccb,dcb in pairs(bcb.Torso:GetChildren())do if dcb:IsA('SpecialMesh')then
dcb:destroy()end end
if
bcb.Head:FindFirstChild('Mesh')then bcb.Head.Mesh:destroy()end;if bcb.Torso:FindFirstChild('Neck')then
bcb.Torso.Neck.C0=
CFrame.new(0,1,0)*CFrame.Angles(math.rad(90),math.rad(180),0)end;if
bcb.Torso:FindFirstChild('Left Shoulder')then
bcb.Torso['Left Shoulder'].C0=CFrame.new(-1,0.5,0)*CFrame.Angles(0,math.rad(
-90),0)end
if
bcb.Torso:FindFirstChild('Right Shoulder')then bcb.Torso['Right Shoulder'].C0=CFrame.new(1,0.5,0)*
CFrame.Angles(0,math.rad(90),0)end;if bcb.Torso:FindFirstChild('Left Hip')then
bcb.Torso['Left Hip'].C0=CFrame.new(
-1,-1,0)*CFrame.Angles(0,math.rad(-90),0)end
if
bcb.Torso:FindFirstChild('Right Hip')then bcb.Torso['Right Hip'].C0=CFrame.new(1,-1,0)*
CFrame.Angles(0,math.rad(90),0)end end
function UPDATE_MODEL(bcb,ccb)
local dcb=bda:GetCharacterAppearanceAsync(bda:GetUserIdFromNameAsync(ccb))bcb.Name=ccb
for _db,adb in pairs(dcb:GetChildren())do
if
adb:IsA('SpecialMesh')or
adb:IsA('BlockMesh')or adb:IsA('CylinderMesh')then adb.Parent=bcb.Head elseif adb:IsA('Decal')then if bcb.Head:FindFirstChild('face')then
bcb.Head.face.Texture=adb.Texture else local bdb=Instance.new('Decal',bcb.Head)
bdb.Texture=adb.Texture end elseif

adb:IsA('BodyColors')or adb:IsA('CharacterMesh')or adb:IsA('Shirt')or adb:IsA('Pants')or
adb:IsA('ShirtGraphic')then
if
bcb:FindFirstChild('Body Colors')then bcb['Body Colors']:destroy()end;adb.Parent=bcb elseif adb:IsA('Accessory')then adb.Parent=bcb
adb.Handle.CFrame=

bcb.Head.CFrame*CFrame.new(0,bcb.Head.Size.Y/2,0)*adb.AttachmentPoint:inverse()end end
if not bcb.Head:FindFirstChild('Mesh')then
local _db=Instance.new('SpecialMesh',bcb.Head)_db.MeshType=Enum.MeshType.Head
_db.Scale=Vector3.new(1.25,1.25,1.25)end end
function CREEPER(bcb)
for ccb,dcb in pairs(bcb.Character:GetChildren())do
if dcb:IsA('Shirt')or
dcb:IsA('Pants')then dcb:destroy()elseif dcb:IsA('ShirtGraphic')then
dcb.Archivable=false;dcb.Graphic=''end end;for ccb,dcb in pairs(bcb.Character:GetChildren())do if dcb:IsA('Accessory')then
dcb:destroy()end end
bcb.Character.Torso.Neck.C0=
CFrame.new(0,1,0)*CFrame.Angles(math.rad(90),math.rad(180),0)
bcb.Character.Torso['Right Shoulder'].C0=CFrame.new(0,-1.5,
-.5)*CFrame.Angles(0,math.rad(90),0)
bcb.Character.Torso['Left Shoulder'].C0=CFrame.new(0,-1.5,-
.5)*CFrame.Angles(0,math.rad(-90),0)
bcb.Character.Torso['Right Hip'].C0=
CFrame.new(0,-1,.5)*CFrame.Angles(0,math.rad(90),0)
bcb.Character.Torso['Left Hip'].C0=
CFrame.new(0,-1,.5)*CFrame.Angles(0,math.rad(-90),0)
for ccb,dcb in pairs(bcb.Character:GetChildren())do if dcb:IsA('Part')and dcb.Name~=
'HumanoidRootPart'then
dcb.BrickColor=BrickColor.new('Bright green')end end end
function SHREK(bcb)
for adb,bdb in pairs(bcb.Character:GetChildren())do
if bdb:IsA('Shirt')or
bdb:IsA('Pants')or bdb:IsA('Accessory')or
bdb:IsA('CharacterMesh')then bdb:destroy()elseif
bdb:IsA('ShirtGraphic')then bdb.Archivable=false;bdb.Graphic=''end end;for adb,bdb in pairs(bcb.Character.Head:GetChildren())do
if
bdb:IsA('Decal')or bdb:IsA('SpecialMesh')then bdb:destroy()end end
if
bcb.Character:FindFirstChild('Shirt Graphic')then
bcb.Character['Shirt Graphic'].Archivable=false;bcb.Character['Shirt Graphic'].Graphic=''end
local ccb=Instance.new('SpecialMesh',bcb.Character.Head)local dcb=Instance.new('Shirt',bcb.Character)
local _db=Instance.new('Pants',bcb.Character)ccb.MeshType='FileMesh'
ccb.MeshId='http://www.roblox.com/asset/?id=19999257'ccb.Offset=Vector3.new(-0.1,0.1,0)
ccb.TextureId='http://www.roblox.com/asset/?id=156397869'dcb.ShirtTemplate='rbxassetid://133078194'
_db.PantsTemplate='rbxassetid://133078204'end
function DUCK(bcb)
for dcb,_db in pairs(bcb.Character:GetChildren())do
if
_db:IsA('Part')and
_db.Name~='Torso'and _db.Name~='HumanoidRootPart'then _db.Transparency=1 elseif _db:IsA('Shirt')or _db:IsA('Pants')or
_db:IsA('Accessory')then _db:destroy()elseif _db:IsA('ShirtGraphic')then
_db.Archivable=false;_db.Graphic=''end end
local ccb=Instance.new('SpecialMesh',bcb.Character.Torso)ccb.MeshType='FileMesh'
ccb.MeshId='http://www.roblox.com/asset/?id=9419831'ccb.TextureId='http://www.roblox.com/asset/?id=9419827'
ccb.Scale=Vector3.new(5,5,5)if bcb.Character.Head:FindFirstChild('face')then
bcb.Character.Head.face.Transparency=1 end end
function DOG(bcb)
for adb,bdb in pairs(bcb.Character:GetChildren())do
if bdb:IsA('Shirt')or
bdb:IsA('Pants')then bdb:destroy()elseif bdb:IsA('ShirtGraphic')then
bdb.Archivable=false;bdb.Graphic=''end end;bcb.Character.Torso.Transparency=1
bcb.Character.Torso.Neck.C0=CFrame.new(0,
-0.5,-2)*CFrame.Angles(math.rad(90),math.rad(180),0)
bcb.Character.Torso['Right Shoulder'].C0=CFrame.new(0.5,-1.5,
-1.5)*CFrame.Angles(0,math.rad(90),0)
bcb.Character.Torso['Left Shoulder'].C0=CFrame.new(-0.5,-
1.5,-1.5)*CFrame.Angles(0,math.rad(-90),0)
bcb.Character.Torso['Right Hip'].C0=
CFrame.new(1.5,-1,1.5)*CFrame.Angles(0,math.rad(90),0)
bcb.Character.Torso['Left Hip'].C0=
CFrame.new(-1.5,-1,1.5)*CFrame.Angles(0,math.rad(-90),0)local ccb=Instance.new('Seat',bcb.Character)
local dcb=Instance.new('BodyForce',ccb)
local _db=Instance.new('Weld',bcb.Character.Torso)ccb.Name='FakeTorso'ccb.FormFactor='Symmetric'ccb.TopSurface=0
ccb.BottomSurface=0;ccb.Size=Vector3.new(3,1,4)
ccb.BrickColor=BrickColor.new('Brown')ccb.CFrame=bcb.Character.Torso.CFrame;dcb.Force=Vector3.new(0,
ccb:GetMass()*196.25,0)
_db.Part0=bcb.Character.Torso;_db.Part1=ccb;_db.C0=CFrame.new(0,-0.5,0)
for adb,bdb in
pairs(bcb.Character:GetChildren())do if bdb:IsA('Part')and bdb.Name~='HumanoidRootPart'then
bdb.BrickColor=BrickColor.new('Brown')end end end
function ALIEN(bcb)
for ccb,dcb in pairs(bcb.Character:GetChildren())do
if dcb:IsA('Shirt')or
dcb:IsA('Pants')or dcb:IsA('Accessory')then
dcb:destroy()elseif dcb:IsA('ShirtGraphic')then dcb.Archivable=false;dcb.Graphic=''elseif dcb:IsA('Part')and
dcb.Name~='HumanoidRootPart'then
dcb.BrickColor=BrickColor.new('Fossil')end end;ALIEN_H:Clone().Parent=bcb.Character end
function DECALSPAM(bcb,ccb)
for dcb,_db in pairs(bcb:GetChildren())do
if _db:IsA('BasePart')then
spawn(function()
local adb={'Back','Bottom','Front','Left','Right','Top'}local bdb=1
for i=1,6 do local cdb=Instance.new('Decal',_db)cdb.Name='decal_seth'cdb.Texture=
'rbxassetid://'..ccb-1;cdb.Face=adb[bdb]bdb=bdb+1 end end)end;DECALSPAM(_db,ccb)end end
function UNDECALSPAM(bcb)
for ccb,dcb in pairs(bcb:GetChildren())do if dcb:IsA('BasePart')then
for _db,adb in
pairs(dcb:GetChildren())do if adb:IsA('Decal')and adb.Name=='decal_seth'then
adb:destroy()end end end
UNDECALSPAM(dcb)end end
function CREATE_DONG(bcb,ccb)if bcb.Character:FindFirstChild('DONG')then
bcb.Character.DONG:destroy()end
local dcb=Instance.new('Model',bcb.Character)dcb.Name='DONG'
local _db=Instance.new('BodyGyro',bcb.Character.Torso)
local adb=Instance.new('Part',bcb.Character['DONG'])local bdb=Instance.new('CylinderMesh',adb)
local cdb=Instance.new('Weld',bcb.Character.Head)
local ddb=Instance.new('Part',bcb.Character['DONG'])local __c=Instance.new('SpecialMesh',ddb)
local a_c=Instance.new('Weld',ddb)
local b_c=Instance.new('Part',bcb.Character['DONG'])local c_c=Instance.new('SpecialMesh',b_c)
local d_c=Instance.new('Weld',b_c)
local _ac=Instance.new('Part',bcb.Character['DONG'])local aac=Instance.new('SpecialMesh',_ac)
local bac=Instance.new('Weld',_ac)adb.TopSurface=0;adb.BottomSurface=0;adb.Name='Main'adb.formFactor=3
adb.Size=Vector3.new(0.6,2.5,0.6)adb.BrickColor=BrickColor.new(ccb)
adb.Position=bcb.Character.Head.Position;adb.CanCollide=false;cdb.Part0=adb;cdb.Part1=bcb.Character.Head
cdb.C0=
CFrame.new(0,0.25,2.1)*CFrame.Angles(math.rad(45),0,0)ddb.Name='Mush'ddb.BottomSurface=0;ddb.TopSurface=0;ddb.FormFactor=3
ddb.Size=Vector3.new(0.6,0.6,0.6)ddb.CFrame=CFrame.new(adb.Position)
ddb.BrickColor=BrickColor.new('Pink')ddb.CanCollide=false;__c.MeshType='Sphere'a_c.Part0=adb;a_c.Part1=ddb
a_c.C0=CFrame.new(0,1.3,0)b_c.Name='Left Ball'b_c.BottomSurface=0;b_c.TopSurface=0
b_c.CanCollide=false;b_c.formFactor=3;b_c.Size=Vector3.new(1,1,1)
b_c.CFrame=CFrame.new(bcb.Character['Left Leg'].Position)b_c.BrickColor=BrickColor.new(ccb)c_c.Parent=b_c
c_c.MeshType='Sphere'd_c.Part0=bcb.Character['Left Leg']d_c.Part1=b_c;d_c.C0=CFrame.new(0,0.5,
-0.5)_ac.Name='Right Ball'_ac.BottomSurface=0
_ac.CanCollide=false;_ac.TopSurface=0;_ac.formFactor=3;_ac.Size=Vector3.new(1,1,1)
_ac.CFrame=CFrame.new(bcb.Character['Right Leg'].Position)_ac.BrickColor=BrickColor.new(ccb)aac.MeshType='Sphere'
bac.Part0=bcb.Character['Right Leg']bac.Part1=_ac;bac.C0=CFrame.new(0,0.5,-0.5)end
function SCALE(bcb,ccb)
if tonumber(ccb)<0.5 then ccb=0.5 elseif tonumber(ccb)>25 then ccb=25 end;local dcb={}for cac,dac in pairs(bcb:GetChildren())do
if dac:IsA('Accessory')then
local _bc=dac:Clone()table.insert(dcb,_bc)dac:destroy()end end
local _db=bcb.Head;local adb=bcb.Torso;local bdb=bcb['Left Arm']local cdb=bcb['Right Arm']
local ddb=bcb['Left Leg']local __c=bcb['Right Leg']local a_c=bcb.HumanoidRootPart;_db.FormFactor=3
adb.FormFactor=3;bdb.FormFactor=3;cdb.FormFactor=3;ddb.FormFactor=3;__c.FormFactor=3
a_c.FormFactor=3;_db.Size=Vector3.new(ccb*2,ccb,ccb)
adb.Size=Vector3.new(ccb*2,ccb*2,ccb)bdb.Size=Vector3.new(ccb,ccb*2,ccb)
cdb.Size=Vector3.new(ccb,ccb*2,ccb)ddb.Size=Vector3.new(ccb,ccb*2,ccb)
__c.Size=Vector3.new(ccb,ccb*2,ccb)a_c.Size=Vector3.new(ccb*2,ccb*2,ccb)
local b_c=Instance.new('Motor6D',adb)local c_c=Instance.new('Motor6D',adb)
local d_c=Instance.new('Motor6D',adb)local _ac=Instance.new('Motor6D',adb)
local aac=Instance.new('Motor6D',adb)local bac=Instance.new('Motor6D',a_c)b_c.Name='Neck'
b_c.Part0=adb;b_c.Part1=_db
b_c.C0=CFrame.new(0,1 *ccb,0)*CFrame.Angles(-1.6,0,3.1)
b_c.C1=CFrame.new(0,-0.5 *ccb,0)*CFrame.Angles(-1.6,0,3.1)c_c.Name='Left Shoulder'c_c.Part0=adb;c_c.Part1=bdb
c_c.C0=
CFrame.new(-1 *ccb,0.5 *ccb,0)*CFrame.Angles(0,-1.6,0)
c_c.C1=CFrame.new(0.5 *ccb,0.5 *ccb,0)*CFrame.Angles(0,-1.6,0)d_c.Name='Right Shoulder'd_c.Part0=adb;d_c.Part1=cdb
d_c.C0=
CFrame.new(1 *ccb,0.5 *ccb,0)*CFrame.Angles(0,1.6,0)
d_c.C1=CFrame.new(-0.5 *ccb,0.5 *ccb,0)*CFrame.Angles(0,1.6,0)_ac.Name='Left Hip'_ac.Part0=adb;_ac.Part1=ddb
_ac.C0=
CFrame.new(-1 *ccb,-1 *ccb,0)*CFrame.Angles(0,-1.6,0)
_ac.C1=CFrame.new(-0.5 *ccb,1 *ccb,0)*CFrame.Angles(0,-1.6,0)aac.Name='Right Hip'aac.Part0=adb;aac.Part1=__c
aac.C0=
CFrame.new(1 *ccb,-1 *ccb,0)*CFrame.Angles(0,1.6,0)
aac.C1=CFrame.new(0.5 *ccb,1 *ccb,0)*CFrame.Angles(0,1.6,0)bac.Name='RootJoint'bac.Part0=a_c;bac.Part1=adb;bac.C0=CFrame.new(0,0,0)*CFrame.Angles(
-1.6,0,-3.1)
bac.C1=
CFrame.new(0,0,0)*CFrame.Angles(-1.6,0,-3.1)for cac,dac in pairs(dcb)do dac.Parent=bcb end end
function CAPE(bcb)if dda.Character:FindFirstChild('Cape')then
dda.Character.Cape:destroy()end;repeat wait()until dda and dda.Character and
dda.Character:FindFirstChild('Torso')
local ccb=dda.Character.Torso;local dcb=Instance.new('Part',ccb.Parent)
dcb.Name='cape_seth'dcb.Anchored=false;dcb.CanCollide=false;dcb.TopSurface=0
dcb.BottomSurface=0;dcb.BrickColor=BrickColor.new(bcb)dcb.Material='Neon'
dcb.FormFactor='Custom'dcb.Size=Vector3.new(0.2,0.2,0.2)
local _db=Instance.new('BlockMesh',dcb)_db.Scale=Vector3.new(9,17.5,0.5)
local adb=Instance.new('Motor',dcb)adb.Part0=dcb;adb.Part1=ccb;adb.MaxVelocity=1;adb.C0=CFrame.new(0,1.75,0)*
CFrame.Angles(0,math.rad(90),0)
adb.C1=
CFrame.new(0,1,.45)*CFrame.Angles(0,math.rad(90),0)local bdb=false
repeat wait(1 /44)local cdb=0.2;local ddb=ccb.Velocity.magnitude
local __c=0.1
if bdb then cdb=
cdb+ ( (ccb.Velocity.magnitude/10)*0.05)+1;bdb=false else bdb=false end
cdb=cdb+math.min(ccb.Velocity.magnitude/30,1)
adb.MaxVelocity=math.min((ccb.Velocity.magnitude/10),0.04)+__c;adb.DesiredAngle=-cdb;if
adb.CurrentAngle<-0.05 and adb.DesiredAngle>-.05 then adb.MaxVelocity=0.04 end
repeat wait()until
adb.CurrentAngle==adb.DesiredAngle or

math.abs(ccb.Velocity.magnitude-ddb)>= (ccb.Velocity.magnitude/10)+1;if ccb.Velocity.magnitude<0.1 then wait(0.1)end until not dcb or
dcb.Parent~=ccb.Parent end
function INFECT(bcb)
for dcb,_db in pairs(bcb.Character:GetChildren())do
Instance.new('Folder',bcb.Character).Name='infected_seth'
if
_db:IsA('Accessory')or _db:IsA('Shirt')or _db:IsA('Pants')then _db:destroy()elseif _db:IsA('ShirtGraphic')then _db.Archivable=false
_db.Graphic=''end end;if bcb.Character.Head:FindFirstChild('face')then
bcb.Character.Head.face.Texture='rbxassetid://7074882'end
for dcb,_db in
pairs(bcb.Character:GetChildren())do
if _db:IsA('Part')and _db.Name~='HumanoidRootPart'then
if
_db.Name==
'Head'or _db.Name=='Left Arm'or _db.Name=='Right Arm'then _db.BrickColor=BrickColor.new('Medium green')elseif

_db.Name=='Torso'or _db.Name=='Left Leg'or _db.Name=='Right Leg'then _db.BrickColor=BrickColor.new('Brown')end end end
local ccb=bcb.Character.Torso.Touched:connect(function(dcb)
if not
dcb.Parent:FindFirstChild('infected_seth')then
local _db=bda:GetPlayerFromCharacter(dcb.Parent)if _db then INFECT(_db)end end end)end
function fWeld(bcb,ccb,dcb,_db,adb,bdb,cdb,ddb,__c,a_c,b_c)local c_c=Instance.new('Weld')c_c.Name=bcb;c_c.Parent=ccb
c_c.Part0=dcb;c_c.Part1=_db
if(adb)then c_c.C0=CFrame.new(bdb,cdb,ddb)*
CFrame.fromEulerAnglesXYZ(__c,a_c,b_c)else
c_c.C1=
CFrame.new(bdb,cdb,ddb)*CFrame.fromEulerAnglesXYZ(__c,a_c,b_c)end;return c_c end
function BANG(bcb)
spawn(function()local ccb=bda.LocalPlayer.Character.Torso
local dcb=bda[bcb].Character.Torso;dcb.Parent.Humanoid.PlatformStand=true
ccb['Left Shoulder']:destroy()local _db=Instance.new('Weld',ccb)_db.Part0=ccb
_db.Part1=ccb.Parent['Left Arm']_db.C0=CFrame.new(-1.5,0,0)_db.Name='Left Shoulder'
ccb['Right Shoulder']:destroy()local adb=Instance.new('Weld',ccb)adb.Part0=ccb
adb.Part1=ccb.Parent['Right Arm']adb.C0=CFrame.new(1.5,0,0)adb.Name='Right Shoulder'
dcb['Left Shoulder']:destroy()local bdb=Instance.new('Weld',dcb)bdb.Part0=dcb
bdb.Part1=dcb.Parent['Left Arm']bdb.C0=CFrame.new(-1.5,0,0)bdb.Name='Left Shoulder'
dcb['Right Shoulder']:destroy()local cdb=Instance.new('Weld',dcb)cdb.Part0=dcb
cdb.Part1=dcb.Parent['Right Arm']cdb.C0=CFrame.new(1.5,0,0)cdb.Name='Right Shoulder'
dcb['Left Hip']:destroy()local ddb=Instance.new('Weld',dcb)ddb.Part0=dcb
ddb.Part1=dcb.Parent['Left Leg']ddb.C0=CFrame.new(-0.5,-2,0)ddb.Name='Left Hip'
dcb['Right Hip']:destroy()local __c=Instance.new('Weld',dcb)__c.Part0=dcb
__c.Part1=dcb.Parent['Right Leg']__c.C0=CFrame.new(0.5,-2,0)__c.Name='Right Hip'
local a_c=Instance.new('Part',ccb)a_c.TopSurface=0;a_c.BottomSurface=0;a_c.CanCollide=false
a_c.BrickColor=BrickColor.new('Pastel brown')a_c.Shape='Ball'a_c.Size=Vector3.new(1,1,1)
local b_c=Instance.new('SpecialMesh',a_c)b_c.MeshType='Sphere'b_c.Scale=Vector3.new(0.4,0.4,0.4)fWeld('weld',ccb,ccb,a_c,true,
-0.2,-1.3,-0.6,0,0,0)
local c_c=a_c:Clone()c_c.Parent=ccb
fWeld('weld',ccb,ccb,c_c,true,0.2,-1.3,-0.6,0,0,0)local d_c=Instance.new('Part',ccb)d_c.TopSurface=0
d_c.BottomSurface=0;d_c.CanCollide=false
d_c.BrickColor=BrickColor.new('Pastel brown')d_c.formFactor='Custom'd_c.Size=Vector3.new(0.4,1.3,0.4)
fWeld('weld',ccb,ccb,d_c,true,0,
-1,-0.52 + (-d_c.Size.y/2),math.rad(-80),0,0)local _ac=a_c:Clone()_ac.BrickColor=BrickColor.new('Pink')
_ac.Mesh.Scale=Vector3.new(0.4,0.62,0.4)_ac.Parent=ccb
fWeld('weld',d_c,d_c,_ac,true,0,0 + (d_c.Size.y/2),0,math.rad(-10),0,0)local aac=Instance.new('CylinderMesh',d_c)
local bac=Instance.new('Part',dcb)bac.TopSurface=0;bac.BottomSurface=0;bac.CanCollide=false
bac.BrickColor=BrickColor.new('Pastel brown')bac.Shape='Ball'bac.Size=Vector3.new(1,1,1)
local cac=Instance.new('SpecialMesh',bac)cac.MeshType='Sphere'cac.Scale=Vector3.new(1.2,1.2,1.2)fWeld('weld',dcb,dcb,bac,true,
-0.5,0.5,-0.6,0,0,0)
local dac=Instance.new('Part',dcb)dac.TopSurface=0;dac.BottomSurface=0;dac.CanCollide=false
dac.BrickColor=BrickColor.new('Pastel brown')dac.Shape='Ball'dac.Size=Vector3.new(1,1,1)
local _bc=Instance.new('SpecialMesh',dac)_bc.MeshType='Sphere'_bc.Scale=Vector3.new(1.2,1.2,1.2)fWeld('weld',dcb,dcb,dac,true,0.5,0.5,
-0.6,0,0,0)
local abc=Instance.new('Part',dcb)abc.TopSurface=0;abc.BottomSurface=0;abc.CanCollide=false
abc.BrickColor=BrickColor.new('Pink')abc.Shape='Ball'abc.Size=Vector3.new(1,1,1)
local bbc=Instance.new('SpecialMesh',abc)bbc.MeshType='Sphere'bbc.Scale=Vector3.new(0.2,0.2,0.2)fWeld('weld',dcb,dcb,abc,true,
-0.5,0.5,-1.2,0,0,0)
local cbc=Instance.new('Part',dcb)cbc.TopSurface=0;cbc.BottomSurface=0;cbc.CanCollide=false
cbc.BrickColor=BrickColor.new('Pink')cbc.Shape='Ball'cbc.Size=Vector3.new(1,1,1)
local dbc=Instance.new('SpecialMesh',cbc)dbc.MeshType='Sphere'dbc.Scale=Vector3.new(0.2,0.2,0.2)fWeld('weld',dcb,dcb,cbc,true,0.5,0.5,
-1.2,0,0,0)
ddb.C1=
CFrame.new(0.2,1.6,0.4)*CFrame.Angles(3.9,-0.4,0)
__c.C1=CFrame.new(-0.2,1.6,0.4)*CFrame.Angles(3.9,0.4,0)
bdb.C1=CFrame.new(-0.2,0.9,0.6)*CFrame.Angles(3.9,-0.2,0)
cdb.C1=CFrame.new(0.2,0.9,0.6)*CFrame.Angles(3.9,0.2,0)
_db.C1=CFrame.new(-0.5,0.7,0)*CFrame.Angles(-0.9,-0.4,0)
adb.C1=CFrame.new(0.5,0.7,0)*CFrame.Angles(-0.9,0.4,0)
if ccb:FindFirstChild('weldx')then ccb.weldx:destroy()end
WE=fWeld('weldx',ccb,ccb,dcb,true,0,-0.9,-1.3,math.rad(-90),0,0)local _cc=dcb.Neck;_cc.C0=CFrame.new(0,1.5,0)*
CFrame.Angles(math.rad(-210),math.rad(180),0)end)
spawn(function()while wait()do
for i=1,6 do WE.C1=WE.C1 *CFrame.new(0,-0.3,0)end
for i=1,6 do WE.C1=WE.C1 *CFrame.new(0,0.3,0)end end end)end;_G.CLICK_TP=false;local cbb=false
__b.KeyDown:connect(function(bcb)
if bcb:byte()==50 then cbb=true end end)
__b.KeyUp:connect(function(bcb)if bcb:byte()==50 then cbb=false end end)
__b.Button1Down:connect(function()
if

_G.CLICK_TP and cbb and __b.Target and dda.Character and dda.Character:FindFirstChild('HumanoidRootPart')then dda.Character.HumanoidRootPart.CFrame=CFrame.new(__b.Hit.p)+
Vector3.new(0,3,0)end end)_da.Outlines=false;if FIND_IN_TABLE(_ba,dda.userId)then
dda:Kick('You\'re on the ban list.')end;for bcb,ccb in pairs(bda:GetPlayers())do
if
FIND_IN_TABLE(_ba,ccb.userId)then table.insert(cba,ccb)else UPDATE_CHAT(ccb)end end
ADD_COMMAND('ff','ff [plr]',{},function(bcb,ccb)
local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
Instance.new('ForceField',bda[adb].Character)end end)
ADD_COMMAND('unff','unff [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
for bdb,cdb in
pairs(bda[adb].Character:GetChildren())do if cdb:IsA('ForceField')then cdb:destroy()end end end end)
ADD_COMMAND('fire','fire [plr] [r] [g] [b]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
for bdb,cdb in
pairs(bda[adb].Character:GetChildren())do
if cdb:IsA('Part')and cdb.Name~='HumanoidRootPart'then
local ddb=Instance.new('Fire',cdb)
if bcb[2]and bcb[3]and bcb[4]then ddb.Color=Color3.new(bcb[2]/255,bcb[3]/255,
bcb[4]/255)
ddb.SecondaryColor=Color3.new(
bcb[2]/255,bcb[3]/255,bcb[4]/255)end end end end end)
ADD_COMMAND('unfire','unfire [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;for cdb,ddb in pairs(bdb:GetChildren())do
for __c,a_c in pairs(ddb:GetChildren())do if
a_c:IsA('Fire')then a_c:destroy()end end end end end)
ADD_COMMAND('sp','sp [plr] [r] [g] [b]',{'sparkles'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in
pairs(dcb)do
for bdb,cdb in pairs(bda[adb].Character:GetChildren())do
if
cdb:IsA('Part')and cdb.Name~='HumanoidRootPart'then
if bcb[2]and bcb[3]and
bcb[4]then
Instance.new('Sparkles',cdb).Color=Color3.new(bcb[2]/255,
bcb[3]/255,bcb[4]/255)else Instance.new('Sparkles',cdb)end end end end end)
ADD_COMMAND('unsp','unsp [plr]',{'unsparkles'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
for bdb,cdb in
pairs(bda[adb].Character:GetChildren())do for ddb,__c in pairs(cdb:GetChildren())do
if __c:IsA('Sparkles')then __c:destroy()end end end end end)
ADD_COMMAND('smoke','smoke [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
Instance.new('Smoke',bda[adb].Character.Torso)end end)
ADD_COMMAND('unsmoke','unsmoke [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
for bdb,cdb in
pairs(bda[adb].Character.Torso:GetChildren())do if cdb:IsA('Smoke')then cdb:destroy()end end end end)
ADD_COMMAND('btools','btools [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
Instance.new('HopperBin',bda[adb].Backpack).BinType=2
Instance.new('HopperBin',bda[adb].Backpack).BinType=3
Instance.new('HopperBin',bda[adb].Backpack).BinType=4 end end)
ADD_COMMAND('god','god [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;if bdb:FindFirstChild('Humanoid')then bdb.Humanoid.MaxHealth=math.huge
bdb.Humanoid.Health=bdb.Humanoid.MaxHealth end end end)
ADD_COMMAND('sgod','sgod [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;if bdb:FindFirstChild('Humanoid')then bdb.Humanoid.MaxHealth=10000000
bdb.Humanoid.Health=bdb.Humanoid.MaxHealth end end end)
ADD_COMMAND('ungod','ungod [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
if bdb:FindFirstChild('Humanoid')then bdb.Humanoid.MaxHealth=100 end end end)
ADD_COMMAND('heal','heal [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;if bdb:FindFirstChild('Humanoid')then
bdb.Humanoid.Health=bdb.Humanoid.MaxHealth end end end)
ADD_COMMAND('freeze','freeze [plr]',{'frz'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
for bdb,cdb in
pairs(dcb)do local ddb=bda[cdb].Character;for __c,a_c in pairs(ddb:GetChildren())do
if
a_c:IsA('Part')and a_c.Name~='HumanoidRootPart'then a_c.Anchored=true end end end end end)
ADD_COMMAND('thaw','thaw [plr]',{'unfreeze','unfrz'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in
pairs(dcb)do
for bdb,cdb in pairs(dcb)do local ddb=bda[cdb].Character
for __c,a_c in pairs(ddb:GetChildren())do if
a_c:IsA('Part')then a_c.Anchored=false end end end end end)
ADD_COMMAND('kill','kill [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;bdb:BreakJoints()end end)
ADD_COMMAND('sound','sound [id]',{},function(bcb,ccb)
for dcb,_db in pairs(cda:GetChildren())do if _db:IsA('Sound')then
_db:Stop()_db:destroy()end end
if bcb[1]:lower()~='off'then
local dcb=Instance.new('Sound',cda)dcb.Name='song_seth'dcb.Archivable=false;dcb.Looped=true;dcb.SoundId='rbxassetid://'..
bcb[1]dcb.Volume=1;dcb:Play()end end)
ADD_COMMAND('volume','volume [int]',{},function(bcb,ccb)for dcb,_db in pairs(cda:GetChildren())do if _db:IsA('Sound')then
_db.Volume=bcb[1]end end end)
ADD_COMMAND('pitch','pitch [int]',{},function(bcb,ccb)for dcb,_db in pairs(cda:GetChildren())do if _db:IsA('Sound')then
_db.Pitch=bcb[1]end end end)
ADD_COMMAND('explode','explode [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;if bdb:FindFirstChild('Torso')then
Instance.new('Explosion',bdb).Position=bdb.Torso.Position end end end)
ADD_COMMAND('invis','invis [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
for cdb,ddb in pairs(bdb:GetChildren())do
if ddb:IsA('Part')and
ddb.Name~='HumanoidRootPart'then ddb.Transparency=1 end;if ddb:IsA('Accessory')and ddb:FindFirstChild('Handle')then
ddb.Handle.Transparency=1 end end
if bdb.Head:FindFirstChild('face')then bdb.Head.face.Transparency=1 end end end)
ADD_COMMAND('vis','vis [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
for cdb,ddb in pairs(bdb:GetChildren())do
if ddb:IsA('Part')and
ddb.Name~='HumanoidRootPart'then ddb.Transparency=0 end;if ddb:IsA('Accessory')and ddb:FindFirstChild('Handle')then
ddb.Handle.Transparency=0 end end
if bdb.Head:FindFirstChild('face')then bdb.Head.face.Transparency=0 end end end)
ADD_COMMAND('goto','goto [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;if bdb then
ccb.Character.HumanoidRootPart.CFrame=bdb.HumanoidRootPart.CFrame end end end)
ADD_COMMAND('bring','bring [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
spawn(function()
for i=0,4 do if bdb then
bdb.HumanoidRootPart.CFrame=ccb.Character.HumanoidRootPart.CFrame end end end)end end)
ADD_COMMAND('tp','tp [plr] [plr]',{},function(bcb,ccb)
local dcb,_db=GET_PLAYER(bcb[1],ccb),GET_PLAYER(bcb[2],ccb)
for adb,bdb in pairs(dcb)do
for cdb,ddb in pairs(_db)do
spawn(function()
for i=0,3 do if bda[bdb].Character and bda[ddb].Character then
bda[bdb].Character.HumanoidRootPart.CFrame=bda[ddb].Character.HumanoidRootPart.CFrame end end end)end end end)
ADD_COMMAND('char','char [plr] [id]',{'charapp'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
bda[adb].CharacterAppearance=
'http://www.roblox.com/Asset/CharacterFetch.ashx?userId='..bcb[2]bda[adb].Character:BreakJoints()end end)
ADD_COMMAND('ws','ws [plr] [int]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;if bdb:FindFirstChild('Humanoid')then
bdb.Humanoid.WalkSpeed=tonumber(bcb[2])end end end)
ADD_COMMAND('time','time [int]',{},function(bcb,ccb)
_da:SetMinutesAfterMidnight(tonumber(bcb[1])*60)end)
ADD_COMMAND('kick','kick [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
table.insert(cba,bda[adb])end end)
ADD_COMMAND('ban','ban [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
table.insert(_ba,bda[adb].userId)table.insert(cba,bda[adb])UPDATE_BANS()end end)
ADD_COMMAND('unban','unban [username]',{},function(bcb,ccb)
if
FIND_IN_TABLE(_ba,game.Players:GetUserIdFromNameAsync(bcb[1]))then
table.remove(_ba,GET_IN_TABLE(_ba,game.Players:GetUserIdFromNameAsync(bcb[1])))end end)
ADD_COMMAND('unlockws','unlock',{'unlock'},function(bcb,ccb)local function dcb(_db)
for adb,bdb in pairs(_db:GetChildren())do if bdb:IsA('BasePart')then
bdb.Locked=false end;dcb(bdb)end end
dcb(cda)end)
ADD_COMMAND('lockws','lock',{'lock'},function(bcb,ccb)local function dcb(_db)
for adb,bdb in pairs(_db:GetChildren())do if bdb:IsA('BasePart')then
bdb.Locked=true end;dcb(bdb)end end;dcb(cda)end)
ADD_COMMAND('unanchorws','unanchor',{'unanchor'},function(bcb,ccb)local function dcb(_db)
for adb,bdb in pairs(_db:GetChildren())do if
bdb:IsA('BasePart')then bdb.Anchored=false end;dcb(bdb)end end
dcb(cda)end)
ADD_COMMAND('anchorws','anchor',{'anchor'},function(bcb,ccb)local function dcb(_db)
for adb,bdb in pairs(_db:GetChildren())do if bdb:IsA('BasePart')then
bdb.Anchored=true end;dcb(bdb)end end
dcb(cda)end)
ADD_COMMAND('hsize','hsize [plr] [int]',{'hatsize'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in
pairs(dcb)do
for bdb,cdb in pairs(bda[adb].Character:GetChildren())do
if
cdb:IsA('Accessory')then for ddb,__c in pairs(cdb.Handle:GetChildren())do
if __c:IsA('SpecialMesh')then __c.Scale=
bcb[2]*Vector3.new(1,1,1)end end end end end end)
ADD_COMMAND('shats','shats [plr]',{'stealhats'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
for bdb,cdb in
pairs(bda[adb].Character:GetChildren())do if cdb:IsA('Accessory')then cdb.Parent=ccb.Character end end end end)
ADD_COMMAND('rhats','rhats [plr]',{'removehats'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in
pairs(dcb)do
for bdb,cdb in pairs(bda[adb].Character:GetChildren())do if
cdb:IsA('Accessory')then cdb:destroy()end end end end)
ADD_COMMAND('firstp','firstp [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
bda[adb].CameraMode='LockFirstPerson'end end)
ADD_COMMAND('thirdp','thirdp [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
bda[adb].CameraMode='Classic'end end)
ADD_COMMAND('chat','chat [plr] [string]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
game.Chat:Chat(bda[adb].Character.Head,GLS(false,1))end end)
ADD_COMMAND('name','name [plr] [string]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
bda[adb].Character.Name=GLS(false,1)end end)
ADD_COMMAND('unname','unname [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
bda[adb].Character.Name=bda[adb].Name end end)
ADD_COMMAND('noname','noname [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
bda[adb].Character.Name=''end end)
ADD_COMMAND('stun','stun [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;bdb.Humanoid.PlatformStand=true end end)
ADD_COMMAND('unstun','unstun [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;bdb.Humanoid.PlatformStand=false end end)
ADD_COMMAND('guest','guest [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
bda[adb].CharacterAppearance='http://www.roblox.com/Asset/CharacterFetch.ashx?userId=1'bdb:BreakJoints()end end)
ADD_COMMAND('noob','noob [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
bda[adb].CharacterAppearance='http://www.roblox.com/Asset/CharacterFetch.ashx?userId=155902847'bdb:BreakJoints()end end)
ADD_COMMAND('damage','damage [plr] [int]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;bdb.Humanoid.Health=bdb.Humanoid.Health-bcb[2]end end)
ADD_COMMAND('view','view [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;cda.CurrentCamera.CameraSubject=bdb end end)
ADD_COMMAND('unview','unview',{},function()
cda.CurrentCamera.CameraSubject=bda.LocalPlayer.Character end)
ADD_COMMAND('nolimbs','nolimbs [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
for cdb,ddb in pairs(bdb:GetChildren())do
if

ddb:IsA('Part')and ddb.Name~='Head'and ddb.Name~='Torso'and ddb.Name~='HumanoidRootPart'then ddb:destroy()end end end end)
ADD_COMMAND('box','box [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;local cdb=Instance.new('SelectionBox',bdb)
cdb.Adornee=cdb.Parent;cdb.Color=BrickColor.new(''.. (bcb[2]))end end)
ADD_COMMAND('unbox','nobox [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
for cdb,ddb in pairs(bda[adb].Character:GetChildren())do if
ddb:IsA('SelectionBox')then ddb:destroy()end end end end)
ADD_COMMAND('ghost','ghost [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
for cdb,ddb in pairs(bdb:GetChildren())do
if ddb:IsA('Part')and
ddb.Name~='HumanoidRootPart'then ddb.Transparency=0.5 elseif ddb:IsA('Accessory')and
ddb:FindFirstChild('Handle')then ddb.Handle.Transparency=0.5 elseif
bdb.Head:FindFirstChild('face')then bdb.Head.face.Transparency=0.5 end end end end)
ADD_COMMAND('sphere','sphere [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;local cdb=Instance.new('SelectionSphere',bdb)
cdb.Adornee=cdb.Parent end end)
ADD_COMMAND('sky','sky [id]',{},function(bcb,ccb)
if bcb[1]then for adb,bdb in pairs(_da:GetChildren())do if bdb:IsA('Sky')then
bdb:destroy()end end
local dcb={'Bk','Dn','Ft','Lf','Rt','Up'}local _db=Instance.new('Sky',_da)
for adb,bdb in pairs(dcb)do _db['Skybox'..bdb]=
'rbxassetid://'..bcb[1]-1 end end end)
ADD_COMMAND('ambient','ambient [r] [g] [b]',{},function(bcb,ccb)if bcb[1]and bcb[2]and bcb[3]then
_da.Ambient=Color3.new(
bcb[1]/255,bcb[2]/255,bcb[3]/255)end end)
ADD_COMMAND('jail','jail [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do if
FIND_IN_TABLE(bba,bda[adb].Name)then return end
table.insert(bba,bda[adb].Name)local bdb=bda[adb].Character;local cdb=JAIL:Clone()cdb.Parent=cda
cdb:MoveTo(bdb.Torso.Position)cdb.Name='JAIL_'..bda[adb].Name
repeat wait()
bdb=bda[adb].Character
if bdb and bdb:FindFirstChild('HumanoidRootPart')and
cdb:FindFirstChild('MAIN')then bdb.HumanoidRootPart.CFrame=
cdb.MAIN.CFrame+Vector3.new(0,1,0)end until not FIND_IN_TABLE(bba,bda[adb].Name)end end)
ADD_COMMAND('unjail','unjail [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do for bdb,cdb in pairs(bba)do
if
cdb==bda[adb].Name then table.remove(bba,bdb)end end;if
cda:FindFirstChild('JAIL_'..bda[adb].Name)then
cda['JAIL_'..bda[adb].Name]:destroy()end end end)
ADD_COMMAND('animation','animation [plr] [id]',{'anim'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in
pairs(dcb)do local bdb=bcb[2]if bcb[2]=='climb'then bdb='180436334'end;if
bcb[2]=='fall'then bdb='180436148'end
if bcb[2]=='jump'then bdb='125750702'end;if bcb[2]=='sit'then bdb='178130996'end
for cdb,ddb in
pairs(bda[adb].Character.Animate:GetChildren())do if ddb:IsA('StringValue')then
for __c,a_c in pairs(ddb:GetChildren())do if a_c:IsA('Animation')then a_c.AnimationId=
'rbxassetid://'..bdb end end end end end end)
ADD_COMMAND('fix','fix [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;RESET_MODEL(bdb)UPDATE_MODEL(bdb,bda[adb].Name)end end)
ADD_COMMAND('creeper','creeper [plr]',{'crpr'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
CREEPER(bda[adb])end end)
ADD_COMMAND('uncreeper','uncreeper [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;RESET_MODEL(bdb)UPDATE_MODEL(bdb,bda[adb].Name)end end)
ADD_COMMAND('shrek','shrek [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
SHREK(bda[adb])end end)
ADD_COMMAND('unshrek','unshrek [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;RESET_MODEL(bdb)UPDATE_MODEL(bdb,bda[adb].Name)end end)local dbb=false
ADD_COMMAND('spam','spam [string]',{},function(bcb,ccb)dbb=true
spawn(function()repeat wait()
bda:Chat(GLS(false,0))until not dbb end)end)
ADD_COMMAND('nospam','nospam',{},function(bcb,ccb)dbb=false end)
ADD_COMMAND('nuke','nuke [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
spawn(function()
if bda[adb]and bdb and bdb:FindFirstChild('Torso')then
local cdb=Instance.new('Part',cda)cdb.Name='nuke_seth'cdb.Anchored=true;cdb.CanCollide=false
cdb.FormFactor='Symmetric'cdb.Shape='Ball'cdb.Size=Vector3.new(1,1,1)
cdb.BrickColor=BrickColor.new('New Yeller')cdb.Transparency=0.5;cdb.Reflectance=0.2;cdb.TopSurface=0
cdb.BottomSurface=0
cdb.Touched:connect(function(__c)if __c and __c.Parent then
local a_c=Instance.new('Explosion',cda)a_c.Position=__c.Position;a_c.BlastRadius=11
a_c.BlastPressure=math.huge end end)local ddb=bdb.Torso.CFrame;cdb.CFrame=ddb;for i=0,111 do
cdb.Size=cdb.Size+Vector3.new(5,5,5)cdb.CFrame=ddb;wait(1 /44)end
cdb:destroy()end end)end end)
ADD_COMMAND('unnuke','nonuke',{},function(bcb,ccb)for dcb,_db in pairs(cda:GetChildren())do if _db.Name=='nuke_seth'then
_db:destroy()end end end)
ADD_COMMAND('infect','infect [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
INFECT(bda[adb])end end)
ADD_COMMAND('uninfect','uninfect [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;RESET_MODEL(bdb)UPDATE_MODEL(bdb,bda[adb].Name)end end)
ADD_COMMAND('duck','duck [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
DUCK(bda[adb])end end)
ADD_COMMAND('unduck','unduck [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;RESET_MODEL(bdb)UPDATE_MODEL(bdb,bda[adb].Name)end end)
ADD_COMMAND('disable','disable [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;if bdb:FindFirstChild('Humanoid')then
bdb.Humanoid.Name='HUMANOID_'..bda[adb].Name;local cdb=bdb['HUMANOID_'..bda[adb].Name]
cdb.Parent=HUMANOIDS end end end)
ADD_COMMAND('enable','enable [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
if bdb:FindFirstChild('Humanoid')then return else
if
HUMANOIDS:FindFirstChild('HUMANOID_'..bda[adb].Name)then
local cdb=HUMANOIDS['HUMANOID_'..bda[adb].Name]cdb.Parent=bdb;cdb.Name='Humanoid'end end end end)
ADD_COMMAND('size','size [plr] [int]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
SCALE(bda[adb].Character,bcb[2])end end)
ADD_COMMAND('clone','clone [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;bdb.Archivable=true;local cdb=bdb:Clone()cdb.Parent=cda
cdb:MoveTo(bdb:GetModelCFrame().p)cdb:MakeJoints()bdb.Archivable=false end end)
ADD_COMMAND('spin','spin [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;for __c,a_c in pairs(bdb.Torso:GetChildren())do if a_c.Name=='SPIN'then
a_c:destroy()end end
local cdb=bdb.Torso;local ddb=Instance.new('BodyGyro',cdb)ddb.Name='SPIN'
ddb.maxTorque=Vector3.new(0,math.huge,0)ddb.P=11111;ddb.cframe=cdb.CFrame
spawn(function()repeat wait(1 /44)ddb.CFrame=ddb.CFrame*
CFrame.Angles(0,math.rad(30),0)until
not ddb or ddb.Parent~=cdb end)end end)
ADD_COMMAND('unspin','unspin [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;for cdb,ddb in pairs(bdb.Torso:GetChildren())do if ddb.Name=='SPIN'then
ddb:destroy()end end end end)
ADD_COMMAND('dog','dog [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
DOG(bda[adb])end end)
ADD_COMMAND('undog','undog [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;RESET_MODEL(bdb)UPDATE_MODEL(bdb,bda[adb].Name)end end)
ADD_COMMAND('loopheal','loopheal [plr]',{'lheal'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
if LOOPED:FindFirstChild(bda[adb].Name..'_heal')then
LOOPED[
bda[adb].Name..'_heal']:destroy()else local cdb=Instance.new('StringValue',LOOPED)cdb.Name=
bda[adb].Name..'_heal'
spawn(function()while wait()do
if
LOOPED:FindFirstChild(bda[adb].Name..'_heal')then bdb.Humanoid.Health=bdb.Humanoid.MaxHealth end end end)end end end)
ADD_COMMAND('unloopheal','unloopheal [plr]',{'unlheal'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in
pairs(dcb)do local bdb=bda[adb].Character;if
LOOPED:FindFirstChild(bda[adb].Name..'_heal')then
LOOPED[bda[adb].Name..'_heal']:destroy()end end end)
ADD_COMMAND('fling','fling [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
if bdb:FindFirstChild('Humanoid')then local cdb;local ddb;repeat
cdb=math.random(-9999,9999)until math.abs(cdb)>=5555;repeat
ddb=math.random(-9999,9999)until math.abs(ddb)>=5555
bdb.Torso.Velocity=Vector3.new(0,0,0)local __c=Instance.new('BodyForce',bdb.Torso)__c.force=Vector3.new(
cdb*4,9999 *5,ddb*4)end end end)
ADD_COMMAND('alien','alien [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
ALIEN(bda[adb])end end)
ADD_COMMAND('nograv','nograv [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;for ddb,__c in pairs(bdb.Torso:GetChildren())do if __c.Name=='nograv'then
__c:destroy()end end
local cdb=Instance.new('BodyForce',bdb.Torso)cdb.Name='nograv_seth'cdb.Force=Vector3.new(0,2500,0)end end)
ADD_COMMAND('grav','grav [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;for cdb,ddb in pairs(bdb.Torso:GetChildren())do if ddb.Name=='nograv_seth'then
ddb:destroy()end end end end)
ADD_COMMAND('cape','cape [brick color]',{},function(bcb,ccb)
spawn(function()if dda.Character:FindFirstChild('Cape')then
dda.Character.Cape:destroy()end
if not bcb[1]then bcb[1]='Deep blue'end;CAPE(GLS(false,1))end)end)
ADD_COMMAND('uncape','uncape',{},function(bcb,ccb)if dda.Character:FindFirstChild('cape_seth')then
dda.Character.cape_seth:destroy()end end)
ADD_COMMAND('paper','paper [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;for cdb,ddb in pairs(bdb:GetChildren())do
if ddb:IsA('Part')and
ddb.Name~='HumanoidRootPart'then PAPER_MESH:Clone().Parent=ddb end end end end)
ADD_COMMAND('punish','punish [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;bdb.Parent=_da end end)
ADD_COMMAND('unpunish','unpunish [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do local bdb=_da[''..
bda[adb].Name]bdb.Parent=cda end end)local _cb=false
ADD_COMMAND('disco','disco',{},function(bcb,ccb)_cb=true
spawn(function()repeat wait(0.5)
_da.Ambient=Color3.new(math.random(),math.random(),math.random())until not _cb end)end)
ADD_COMMAND('undisco','undisco',{},function(bcb,ccb)_cb=false end)
ADD_COMMAND('team','team [plr] [team]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
for bdb,cdb in
pairs(game.Teams:GetChildren())do if string.lower(cdb.Name)==GLS(true,1)then
bda[adb].Team=cdb end end end end)
ADD_COMMAND('jp','jp [plr] [int]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
if bdb:FindFirstChild('Humanoid')then bdb.Humanoid.JumpPower=bcb[2]end end end)
ADD_COMMAND('smallhead','smallhead [plr]',{'shead'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;bdb.Head.Mesh.Scale=Vector3.new(0.5,0.5,0.5)bdb.Head.Mesh.Offset=Vector3.new(0,
-0.25,0)end end)
ADD_COMMAND('bighead','bighead [plr]',{'bhead'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;bdb.Head.Mesh.Scale=Vector3.new(2.25,2.25,2.25)
bdb.Head.Mesh.Offset=Vector3.new(0,0.5,0)end end)
ADD_COMMAND('headsize','headsize [plr] [int]',{'hsize'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in
pairs(dcb)do local bdb=bda[adb].Character
if bcb[2]==1 then
bdb.Head.Mesh.Scale=Vector3.new(1.25,1.25,1.25)bdb.Head.Mesh.Offset=Vector3.new(0,0,0)else bdb.Head.Mesh.Scale=
bcb[2]*Vector3.new(1.25,1.25,1.25)end end end)
ADD_COMMAND('fixhead','fixhead [plr]',{'fhead'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;bdb.Head.Mesh.Scale=Vector3.new(1.25,1.25,1.25)
bdb.Head.Mesh.Offset=Vector3.new(0,0,0)bdb.Head.Transparency=0;if bdb.Head:FindFirstChild('face')then
bdb.Head.face.Transparency=0 end end end)
ADD_COMMAND('removehead','removehead [plr]',{'rhead'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in
pairs(dcb)do local bdb=bda[adb].Character;bdb.Head.Transparency=1;if
bdb.Head:FindFirstChild('face')then bdb.Head.face.Transparency=1 end end end)
ADD_COMMAND('stealtools','stealtools [plr]',{'stools'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in
pairs(dcb)do for bdb,cdb in pairs(bda[adb].Backpack:GetChildren())do
if
cdb:IsA('Tool')or cdb:IsA('HopperBin')then cdb.Parent=dda.Backpack end end end end)
ADD_COMMAND('removetools','removetools [plr]',{'rtools'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in
pairs(dcb)do for bdb,cdb in pairs(bda[adb].Backpack:GetChildren())do
if
cdb:IsA('Tool')or cdb:IsA('HopperBin')then cdb:destroy()end end end end)
ADD_COMMAND('clonetools','clonetools [plr]',{'ctools'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in
pairs(dcb)do
for bdb,cdb in pairs(bda[adb].Backpack:GetChildren())do if
cdb:IsA('Tool')or cdb:IsA('HopperBin')then
cdb:Clone().Parent=dda.Backpack end end end end)
ADD_COMMAND('dong','dong [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
if bcb[2]=='black'then CREATE_DONG(bda[adb],'Brown')end
if bcb[2]=='asian'then CREATE_DONG(bda[adb],'Cool yellow')end
if bcb[2]=='alien'then CREATE_DONG(bda[adb],'Lime green')end
if bcb[2]=='frozen'then CREATE_DONG(bda[adb],1019)end
if not bcb[2]then CREATE_DONG(bda[adb],'Pastel brown')end end end)
ADD_COMMAND('particles','particles [plr] [id]',{'pts'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in
pairs(dcb)do local bdb=bda[adb].Character
for cdb,ddb in
pairs(bdb.Torso:GetChildren())do if ddb:IsA('ParticleEmitter')then ddb:destroy()end end
Instance.new('ParticleEmitter',bdb.Torso).Texture=
'http://www.roblox.com/asset/?id='..bcb[2]-1 end end)
ADD_COMMAND('rocket','rocket [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
spawn(function()local cdb=ROCKET:Clone()cdb.Parent=cda
local ddb=Instance.new('Weld',cdb)ddb.Part0=ddb.Parent;ddb.Part1=bdb.Torso
ddb.C1=CFrame.new(0,0.5,1)cdb.force.Force=Vector3.new(0,15000,0)wait()
bdb.HumanoidRootPart.CFrame=
bdb.HumanoidRootPart.CFrame*CFrame.new(0,5,0)wait(5)
Instance.new('Explosion',cdb).Position=cdb.Position;wait(1)cdb:destroy()end)end end)
ADD_COMMAND('blackify','blackify [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
COLOR(bda[adb],'Really black')end end)
ADD_COMMAND('whitify','whitify [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
COLOR(bda[adb],'White')end end)
ADD_COMMAND('color','color [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
COLOR(bda[adb],GLS(false,1))end end)
ADD_COMMAND('sword','sword [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
ECOMMAND('gear '..
bda[adb].Name..' 125013769')end end)
ADD_COMMAND('change','change [plr] [stat] [int/string]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
if
bda[adb]:FindFirstChild('leaderstats')then
for bdb,cdb in pairs(bda[adb].leaderstats:GetChildren())do
if

string.lower(cdb.Name)==string.lower(bcb[2])and cdb:IsA('IntValue')or cdb:IsA('NumberValue')then if bcb[3]then
cdb.Value=tonumber(bcb[3])end elseif
string.lower(cdb.Name)==string.lower(bcb[2])and cdb:IsA('StringValue')then
cdb.Value=GLS(false,2)end end end end end)
ADD_COMMAND('bait','bait',{},function(bcb,ccb)
spawn(function()local dcb=Instance.new('Model',cda)
dcb.Name='Touch For Admin!'local _db=Instance.new('Part',dcb)_db.Name='Head'
_db.Position=ccb.Character.Head.Position;_db.BrickColor=BrickColor.new('Pink')_db.Material='Neon'
local adb=Instance.new('Humanoid',dcb)
_db.Touched:connect(function(bdb)
if bdb.Parent.Name~=ccb.Name or
bdb.Parent.Name~=dda.Name then if bdb.Parent:FindFirstChild('Humanoid')then
bdb.Parent.Humanoid:destroy()end end end)end)end)
ADD_COMMAND('naked','naked [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
for cdb,ddb in pairs(bdb:GetChildren())do if

ddb:IsA('Accessory')or ddb:IsA('Shirt')or ddb:IsA('Pants')or ddb:IsA('ShirtGraphic')then ddb:destroy()end
for __c,a_c in
pairs(bdb.Torso:GetChildren())do if a_c:IsA('Decal')then a_c:destroy()end end end end end)
ADD_COMMAND('decalspam','decalspam [decal]',{'dspam'},function(bcb,ccb)
if bcb[1]then DECALSPAM(cda,bcb[1])end end)
ADD_COMMAND('undecalspam','undecalspam',{'undspam'},function(bcb,ccb)if bcb[1]then UNDECALSPAM(cda)end end)
ADD_COMMAND('bang','bang [plr]',{'rape'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
BANG(bda[adb].Name)end end)
ADD_COMMAND('lag','lag [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
LAG(bda[adb])end end)
ADD_COMMAND('respawn','respawn [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=Instance.new('Model',cda)bdb.Name='respawn_seth'local cdb=Instance.new('Part',bdb)
cdb.Name='Torso'cdb.CanCollide=false;cdb.Transparency=1
Instance.new('Humanoid',bdb)bda[adb].Character=bdb end end)
ADD_COMMAND('face','face [plr] [decal]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;for ddb,__c in pairs(bdb.Head:GetChildren())do if __c:IsA('Decal')then
__c:destroy()end end
local cdb=Instance.new('Decal',bdb.Head)cdb.Name='face'cdb.Texture='rbxassetid://'..bcb[2]-1 end end)
ADD_COMMAND('shirt','shirt [plr] [decal]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;for ddb,__c in pairs(bdb:GetChildren())do
if __c:IsA('Shirt')then __c:destroy()end end
local cdb=Instance.new('Shirt',bdb)cdb.Name='Shirt'
cdb.ShirtTemplate='rbxassetid://'..bcb[2]-1 end end)
ADD_COMMAND('pants','pants [plr] [decal]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;for ddb,__c in pairs(bdb:GetChildren())do
if __c:IsA('Pants')then __c:destroy()end end
local cdb=Instance.new('Pants',bdb)cdb.Name='Shirt'
cdb.PantsTemplate='rbxassetid://'..bcb[2]-1 end end)
ADD_COMMAND('longneck','longneck [plr]',{'lneck','giraffe'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in
pairs(dcb)do local bdb=bda[adb].Character;RESET_MODEL(bdb)
UPDATE_MODEL(bdb,bda[adb].Name)
for a_c,b_c in pairs(bdb:GetChildren())do if b_c:IsA('Accessory')then
b_c.Handle.Mesh.Offset=Vector3.new(0,5,0)end end;if bdb.Head:FindFirstChild('Mesh')then
bdb.Head.Mesh.Offset=Vector3.new(0,5,0)end
local cdb=Instance.new('Part',bdb)cdb.Name='giraffe_seth'cdb.BrickColor=bdb.Head.BrickColor
cdb.Size=Vector3.new(2,1,1)local ddb=Instance.new('SpecialMesh',cdb)
ddb.Scale=Vector3.new(1.25,5,1.25)ddb.Offset=Vector3.new(0,2,0)
local __c=Instance.new('Weld',cdb)__c.Part0=bdb.Head;__c.Part1=cdb end end)
ADD_COMMAND('stealchar','stealchar [plr]',{'schar'},function(bcb,ccb)local dcb,_db=GET_PLAYER(bcb[1])
for adb,bdb in pairs(dcb)do
RESET_MODEL(ccb.Character)UPDATE_MODEL(ccb.Character,bda[bdb].Name)end end)
ADD_COMMAND('baseplate','baseplate',{'bp'},function(bcb,ccb)for _db,adb in pairs(cda:GetChildren())do
if adb:IsA('Model')and
adb.Name=='baseplate_seth'then adb:destroy()end end
local dcb=Instance.new('Part',cda)dcb.Name='baseplate_seth'dcb.Anchored=true
dcb.BrickColor=BrickColor.new('Bright green')dcb.Size=Vector3.new(2048,5,2048)
dcb.Position=Vector3.new(0,0,0)end)
ADD_COMMAND('norotate','norotate [plr]',{'nrt'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
if bdb:FindFirstChild('Humanoid')then bdb.Humanoid.AutoRotate=false end end end)
ADD_COMMAND('rotate','rotate [plr]',{'rt'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
if bdb:FindFirstChild('Humanoid')then bdb.Humanoid.AutoRotate=true end end end)
ADD_COMMAND('admin','admin [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
if not
CHECK_ADMIN(bda[adb])then table.insert(daa,bda[adb].userId)
UPDATE_ADMINS()
spawn(function()
game.Chat:Chat(bda[adb].Character.Head,STUFF..'You\'re now an admin!')wait(3)
game.Chat:Chat(bda[adb].Character.Head,STUFF..
'Give me a try! | '..d_b..'ff me')end)end end end)
ADD_COMMAND('unadmin','unadmin [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
if
CHECK_ADMIN(bda[adb])then
if FIND_IN_TABLE(daa,bda[adb].userId)then
table.remove(daa,GET_IN_TABLE(daa,bda[adb].userId))UPDATE_ADMINS()
game.Chat:Chat(bda[adb].Character.Head,STUFF..
'You\'re no longer an admin.')end end end end)
ADD_COMMAND('minzoom','minzoom [plr] [int]',{'minz'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
bda[adb].CameraMinZoomDistance=bcb[2]end end)
ADD_COMMAND('maxzoom','maxzoom [plr] [int]',{'maxz'},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
bda[adb].CameraMaxZoomDistance=bcb[2]end end)
ADD_COMMAND('age','age [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
NOTIFY(
bda[adb].Name..' | '..bda[adb].AccountAge,255,255,255)end end)
ADD_COMMAND('hl','hl [plr] [r] [g] [b]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
if bdb:FindFirstChild('Torso')then
local cdb=Instance.new('SpotLight',bdb.Torso)cdb.Name='seth_hl'cdb.Brightness=5;cdb.Range=60;if
bcb[2]and bcb[3]and bcb[4]then
cdb.Color=Color3.new(bcb[2]/255,bcb[3]/255,bcb[4]/255)end end end end)
ADD_COMMAND('unhl','unhl [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
if bdb:FindFirstChild('Torso')then for cdb,ddb in pairs(bdb.Torso:GetChildren())do
if
ddb:IsA('SpotLight')and ddb.Name=='seth_hl'then ddb:destroy()end end end end end)
ADD_COMMAND('crash','crash [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character;bdb.Torso.Anchored=true
for cdb,ddb in pairs(bdb:GetChildren())do if
ddb:IsA('Humanoid')then ddb.HipHeight=1 /0 *0 end end end end)
ADD_COMMAND('shutdown','shutdown',{},function(bcb,ccb)cda.Gravity=1 /0 *0 end)
ADD_COMMAND('fr','fr [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)for _db,adb in pairs(dcb)do
if not
FIND_IN_TABLE(aba,bda[adb].Name)then table.insert(aba,bda[adb].Name)end end end)
ADD_COMMAND('unfr','unfr [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
if
FIND_IN_TABLE(aba,bda[adb].Name)then
spawn(function()
table.remove(aba,GET_IN_TABLE(aba,bda[adb].Name))wait(0.5)
bda.LocalPlayer:RevokeFriendship(bda[adb])end)end end end)
ADD_COMMAND('smite','smite [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
spawn(function()
local function cdb(cac,dac,_bc)local abc=dac-cac;return
workspace:FindPartOnRayWithIgnoreList(Ray.new(cac,abc.unit*
math.min(abc.magnitude,999)),_bc or{},false,true)end
local ddb=bdb.PrimaryPart.Position-Vector3.new(0,3,0)local __c=Instance.new('Sound',cda)
__c.SoundId='rbxassetid://178090362'__c.Volume=1;__c:Play()
spawn(function()wait(7)__c:destroy()end)
local a_c,b_c=cdb(ddb,ddb-Vector3.new(0,9,0),{bdb})local c_c=Instance.new('Part',game.Workspace)
c_c.BrickColor=BrickColor.new('Institutional white')c_c.Material='Neon'c_c.Transparency=0.9;c_c.FormFactor=3
c_c.Anchored=true;c_c.CanCollide=false;c_c.Size=Vector3.new(0.2,0.2,0.2)
c_c.CFrame=CFrame.new((
a_c and b_c or ddb)+Vector3.new(0,1e3,0))
Instance.new('BlockMesh',c_c).Scale=Vector3.new(10,10000,10)
local d_c,_ac,aac,bac=c_c:Clone(),c_c:Clone(),c_c:Clone(),c_c:Clone()
for cac,dac in next,{d_c,_ac,aac,bac}do cac=cac*0.1
dac.Parent,dac.Size=c_c,Vector3.new(0.2 +cac,0.2,0.2 +cac)dac.CFrame=c_c.CFrame end;wait(0.5)c_c:destroy()bdb:BreakJoints()end)end end)
ADD_COMMAND('skydive','skydive [plr]',{},function(bcb,ccb)local dcb=GET_PLAYER(bcb[1],ccb)
for _db,adb in pairs(dcb)do
local bdb=bda[adb].Character
spawn(function()for i=0,3 do
if bdb then bdb.HumanoidRootPart.CFrame=bdb.HumanoidRootPart.CFrame+
Vector3.new(0,7500,0)end end end)end end)
ADD_COMMAND('gravity','gravity [int]',{},function(bcb,ccb)cda.Gravity=bcb[1]end)
ADD_COMMAND('fixlighting','fixlighting',{'fixl'},function(bcb,ccb)FIX_LIGHTING()end)
ADD_COMMAND('fixfog','fixfog',{'clrfog'},function(bcb,ccb)
_da.FogColor=Color3.new(191 /255,191 /255,191 /255)_da.FogEnd=100000000;_da.FogStart=0 end)
ADD_COMMAND('day','day',{},function(bcb,ccb)_da.TimeOfDay=14 end)
ADD_COMMAND('night','night',{},function(bcb,ccb)_da.TimeOfDay=24 end)
ADD_COMMAND('serverlock','serverlock',{'slock'},function(bcb,ccb)aab=true end)
ADD_COMMAND('unserverlock','unserverlock',{'unslock'},function(bcb,ccb)aab=false end)
ADD_COMMAND('fogend','fogend [int]',{},function(bcb,ccb)_da.FogEnd=bcb[1]end)
ADD_COMMAND('fogcolor','fogcolor [r] [g] [b]',{},function(bcb,ccb)if bcb[1]and bcb[2]and bcb[3]then
_da.FogColor=Color3.new(
bcb[1]/255,bcb[2]/255,bcb[3]/255)end end)
ADD_COMMAND('noclip','noclip',{},function(bcb,ccb)bab=true;cab=false;dab=false end)
ADD_COMMAND('clip','clip',{},function(bcb,ccb)bab=false end)
ADD_COMMAND('jesusfly','jesusfly',{},function(bcb,ccb)bab=false;cab=true;dab=false end)
ADD_COMMAND('nojfly','nojfly',{},function(bcb,ccb)cab=false end)
ADD_COMMAND('swim','swim',{},function(bcb,ccb)bab=false;cab=false;dab=true end)
ADD_COMMAND('noswim','noswim',{},function(bcb,ccb)dab=false end)
ADD_COMMAND('fly','fly',{},function(bcb,ccb)sFLY()end)
ADD_COMMAND('unfly','unfly',{},function(bcb,ccb)NOFLY()end)
ADD_COMMAND('prefix','prefix [string]',{},function(bcb,ccb)if bcb[1]then d_b=bcb[1]
NOTIFY('Changed prefix to \''..bcb[1]..'\'',255,255,255)end end)
ADD_COMMAND('version','version',{},function(bcb,ccb)
NOTIFY('VERSION | '..dba,255,255,255)end)
ADD_COMMAND('fe','fe',{},function(bcb,ccb)spawn(function()CHECK_FE()end)end)
ADD_COMMAND('serverinfo','serverinfo',{'sinfo'},function(bcb,ccb)if not dca:FindFirstChild('seth_main')then
OPEN_MAIN()end
SETH_MAIN.main.server_h.Visible=true;SETH_MAIN.main.admins_h.Visible=false
SETH_MAIN.main.changelog_h.Visible=false;SETH_MAIN.main.commands_h.Visible=false
SETH_MAIN.main.bans_h.Visible=false;SETH_MAIN.main.credits_h.Visible=false
SETH_MAIN.main.search.Visible=false end)
ADD_COMMAND('admins','admins',{},function(bcb,ccb)if not dca:FindFirstChild('seth_main')then
OPEN_MAIN()end
SETH_MAIN.main.server_h.Visible=false;SETH_MAIN.main.admins_h.Visible=true
SETH_MAIN.main.changelog_h.Visible=false;SETH_MAIN.main.commands_h.Visible=false
SETH_MAIN.main.bans_h.Visible=false;SETH_MAIN.main.credits_h.Visible=false
SETH_MAIN.main.search.Visible=false end)
ADD_COMMAND('changelog','changelog',{},function(bcb,ccb)if not dca:FindFirstChild('seth_main')then
OPEN_MAIN()end
SETH_MAIN.main.server_h.Visible=false;SETH_MAIN.main.admins_h.Visible=false
SETH_MAIN.main.changelog_h.Visible=true;SETH_MAIN.main.commands_h.Visible=false
SETH_MAIN.main.bans_h.Visible=false;SETH_MAIN.main.credits_h.Visible=false
SETH_MAIN.main.search.Visible=false end)
ADD_COMMAND('cmds','cmds',{'commands'},function(bcb,ccb)if not dca:FindFirstChild('seth_main')then
OPEN_MAIN()end
SETH_MAIN.main.server_h.Visible=false;SETH_MAIN.main.admins_h.Visible=false
SETH_MAIN.main.changelog_h.Visible=false;SETH_MAIN.main.commands_h.Visible=true
SETH_MAIN.main.bans_h.Visible=false;SETH_MAIN.main.credits_h.Visible=false
SETH_MAIN.main.search.Visible=true end)
ADD_COMMAND('bans','bans',{},function(bcb,ccb)if not dca:FindFirstChild('seth_main')then
OPEN_MAIN()end
SETH_MAIN.main.server_h.Visible=false;SETH_MAIN.main.admins_h.Visible=false
SETH_MAIN.main.changelog_h.Visible=false;SETH_MAIN.main.commands_h.Visible=false
SETH_MAIN.main.bans_h.Visible=true;SETH_MAIN.main.credits_h.Visible=false
SETH_MAIN.main.search.Visible=false end)
ADD_COMMAND('credits','credits',{},function(bcb,ccb)if not dca:FindFirstChild('seth_main')then
OPEN_MAIN()end
SETH_MAIN.main.server_h.Visible=false;SETH_MAIN.main.admins_h.Visible=false
SETH_MAIN.main.changelog_h.Visible=false;SETH_MAIN.main.commands_h.Visible=false
SETH_MAIN.main.bans_h.Visible=false;SETH_MAIN.main.credits_h.Visible=true
SETH_MAIN.main.search.Visible=false end)
__b.KeyDown:connect(function(bcb)
if bcb:byte()==29 then if not bab then ECOMMAND('noclip')elseif bab then
ECOMMAND('clip')end elseif bcb:byte()==30 then if not cab then
ECOMMAND('jesusfly')elseif cab then ECOMMAND('nojfly')end end end)
function CHECK_FE()
if not cda.FilteringEnabled then
NOTIFY('Filtering is disabled',50,255,50)elseif cda.FilteringEnabled then NOTIFY('Filtering is ENABLED',255,50,50)end end
CMD_BAR:TweenPosition(UDim2.new(0,0,1,-50),'InOut','Quad',0.5,true)local acb=true
CMD_BAR.Changed:connect(function()
if

CMD_BAR.Text~='press ; to execute a command'and CMD_BAR.Focused and not acb then
if CMD_BAR.Text~=''then
if not CMD_BAR.Text:find(' ')then
CMD_BAR.commands.Visible=true;CMD_BAR.commands:ClearAllChildren()
CMD_BAR.commands.CanvasSize=UDim2.new(0,0,0,0)local bcb=0
for ccb,dcb in pairs(b_b)do
if dcb.N:find(CMD_BAR.Text)then
CMD_BAR.commands:TweenSize(UDim2.new(1,0,1,
-200),'InOut','Quad',0.2,true)
CMD_BAR.commands.CanvasSize=CMD_BAR.commands.CanvasSize+UDim2.new(0,0,0,20)local _db=CMD_BAR.commands_ex:Clone()
_db.Position=UDim2.new(0,0,0,bcb)_db.Visible=true;_db.Text=' '..dcb.D;_db.Parent=CMD_BAR.commands;bcb=
bcb+20 end end end else
CMD_BAR.commands:TweenSize(UDim2.new(1,0,0,0),'InOut','Quad',0.2,true)CMD_BAR.commands:ClearAllChildren()
CMD_BAR.commands.CanvasSize=UDim2.new(0,0,0,0)end end end)
CMD_BAR.FocusLost:connect(function()acb=true
if CMD_BAR.Text~=''then spawn(function()
ECOMMAND(CMD_BAR.Text,dda)end)end;CMD_BAR.commands:ClearAllChildren()
CMD_BAR.commands.CanvasSize=UDim2.new(0,0,0,0)
CMD_BAR.commands:TweenSize(UDim2.new(1,0,0,0),'InOut','Quad',0.2,true)
CMD_BAR:TweenPosition(UDim2.new(0,-225,1,-50),'InOut','Quad',0.5,true)end)
__b.KeyDown:connect(function(bcb)
if bcb:byte()==59 then acb=false
CMD_BAR:TweenPosition(UDim2.new(0,0,1,-50),'InOut','Quad',0.5,true)CMD_BAR:CaptureFocus()end end)
NOTIFY('Hello, '..bda.LocalPlayer.Name,255,255,255)CHECK_FE()
end)

jpower.Name = "jpower"
jpower.Parent = scriptframe
jpower.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
jpower.BorderSizePixel = 0
jpower.Position = UDim2.new(0.536509514, 0, 0.258389235, 0)
jpower.Size = UDim2.new(0, 101, 0, 19)
jpower.Font = Enum.Font.Code
jpower.Text = "100JPower"
jpower.TextColor3 = Color3.new(0, 0.0980392, 1)
jpower.TextScaled = true
jpower.TextSize = 25
jpower.TextWrapped = true
jpower.MouseButton1Down:connect(function()
while wait()do
service.Players.LocalPlayer.Character.Humanoid.JumpPower=Jump 
end 
end)

sellplanks.Name = "sellplanks"
sellplanks.Parent = scriptframe
sellplanks.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
sellplanks.BorderSizePixel = 0
sellplanks.Position = UDim2.new(0.532912374, 0, 0.0167784691, 0)
sellplanks.Size = UDim2.new(0, 101, 0, 19)
sellplanks.Font = Enum.Font.Code
sellplanks.Text = "Sell Planks"
sellplanks.TextColor3 = Color3.new(0, 0.0980392, 1)
sellplanks.TextScaled = true
sellplanks.TextSize = 25
sellplanks.TextWrapped = true
sellplanks.MouseButton1Down:connect(function()
	for _, Plank in pairs(service.Workspace.PlayerModels:GetChildren()) do
		if Plank.Name=="Plank" and Plank.Owner.Value==service.Players.LocalPlayer then
				for i,v in pairs(Plank:GetChildren()) do
					if v.Name=="WoodSection" then
						spawn(function()
							for i=1,10 do
								wait()
								v.CFrame=CFrame.new(Vector3.new(315, -0.296, 85.791))*CFrame.Angles(math.rad(90),0,0)
							end
						end)
					end
				end
				spawn(function()
					for i=1,20 do
						wait()
						service.ReplicatedStorage.Interaction.ClientIsDragging:FireServer(Plank)
					end
				end)
			end
		end
end)

sideland.Name = "sideland"
sideland.Parent = scriptframe
sideland.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
sideland.BorderSizePixel = 0
sideland.Position = UDim2.new(0.0720892623, 0, 0.258389264, 0)
sideland.Size = UDim2.new(0, 101, 0, 19)
sideland.Font = Enum.Font.Code
sideland.Text = "Side Land"
sideland.TextColor3 = Color3.new(0, 0.0980392, 1)
sideland.TextScaled = true
sideland.TextSize = 25
sideland.TextWrapped = true
sideland.MouseButton1Down:connect(function()
--base plots spawn sideways
for i,v in pairs(game.Workspace.Properties:GetChildren()) do
    if v.Owner.Value == game.Players.LocalPlayer then
game.ReplicatedStorage.PropertyPurchasing.ClientExpandedProperty:FireServer(v,CFrame.new(game.Players.LocalPlayer.Character["Left Leg"].Position)*CFrame.Angles(0,0,math.rad(90)))
    end
end
end)

normland.Name = "normland"
normland.Parent = scriptframe
normland.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
normland.BorderSizePixel = 0
normland.Position = UDim2.new(0.0720892623, 0, 0.130872488, 0)
normland.Size = UDim2.new(0, 101, 0, 19)
normland.Font = Enum.Font.Code
normland.Text = "Normal Land"
normland.TextColor3 = Color3.new(0, 0.0980392, 1)
normland.TextScaled = true
normland.TextSize = 25
normland.TextWrapped = true
normland.MouseButton1Down:connect(function()
_G.TPStuff = true
while _G.TPStuff == true do
wait(5)
for i,v in pairs(game.Workspace.Properties:GetChildren()) do
    if v.Owner.Value == game.Players.LocalPlayer then
        game.ReplicatedStorage.PropertyPurchasing.ClientExpandedProperty:FireServer(v,CFrame.new(game.Players.LocalPlayer.Character["Left Leg"].Position))
    end
end
end
end)

ozhub.Name = "ozhub"
ozhub.Parent = scriptframe
ozhub.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
ozhub.BorderSizePixel = 0
ozhub.Position = UDim2.new(0.068492204, 0, 0.0167785324, 0)
ozhub.Size = UDim2.new(0, 101, 0, 19)
ozhub.Font = Enum.Font.Code
ozhub.Text = "Ozfinity Hub"
ozhub.TextColor3 = Color3.new(0, 0.0980392, 1)
ozhub.TextScaled = true
ozhub.TextSize = 25
ozhub.TextWrapped = true
ozhub.MouseButton1Down:connect(function()
loadstring(game:GetObjects('rbxassetid://1151665021')[1].Source)()
end)

harddrag.Name = "harddrag"
harddrag.Parent = scriptframe
harddrag.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
harddrag.BorderSizePixel = 0
harddrag.Position = UDim2.new(0.532520831, 0, 0.49999997, 0)
harddrag.Size = UDim2.new(0, 101, 0, 19)
harddrag.Font = Enum.Font.Code
harddrag.Text = "HardDragger"
harddrag.TextColor3 = Color3.new(0, 0.0980392, 1)
harddrag.TextScaled = true
harddrag.TextSize = 25
harddrag.TextWrapped = true
harddrag.MouseButton1Down:connect(function()
local player = game.Players.LocalPlayer
local Character = player.Character or player.CharacterAdded:wait()
local Humanoid = Character:WaitForChild("Humanoid")
local walkSpeed = Humanoid.WalkSpeed
game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.Dragger.Disabled = true
_G.dragRangeMin = 5
fivefour = coroutine.wrap(function()
EKey = false
QKey = false
player:GetMouse().KeyDown:connect(function(key)
	if string.lower(key) == "e" then
		EKey = true
	elseif string.lower(key) == "q" then
		QKey = true
	end
end)
player:GetMouse().KeyUp:connect(function(key)
	if string.lower(key) == "e" then
		EKey = false
	elseif string.lower(key) == "q" then
		QKey = false
	end
end)
while wait(0.1) do
	if EKey then
		F = FVal
		FVal = FVal + 1000
		ChangeForce(F+1000)
		print(F)
	end
	if QKey then
		F = FVal
		FVal = FVal - 1000
		ChangeForce(F-1000)
		print(F)
	end
end

end)
fivefour()
local dragPart = Instance.new("Part",game.Players.LocalPlayer.PlayerGui)--game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.Dragger.Dragger
dragPart.Size = Vector3.new(0.2,0.2,0.2)
dragPart.BrickColor = BrickColor.new("Really red")
player.CharacterAdded:connect(function()
	Character = player.Character
	Humanoid = Character:WaitForChild("Humanoid")
	Humanoid.Died:connect(function()
		dragPart.Parent = nil
	end)
end)

wait(1)
local dragRangeMax = 10000
local dragRangeMin = _G.dragRangeMin

local camera = workspace.CurrentCamera
local mouse = player:GetMouse()

local button1Down = false
local dragRange = dragRangeMax
FVal = 80000
local bodyPosition = Instance.new("BodyPosition", dragPart)
bodyPosition.maxForce = Vector3.new(1, 1, 1) * FVal
bodyPosition.D = 1000
bodyPosition.P = 4000
function ChangeForce(F)
if F > 0 then
F = bodyPosition.maxForce.X+F
bodyPosition.maxForce = Vector3.new(1, 1, 1) * F
else
F = bodyPosition.maxForce.X-F
bodyPosition.maxForce = Vector3.new(1, 1, 1) * F
end
end

local bodyGyro = Instance.new("BodyGyro", dragPart) 
bodyGyro.maxTorque = Vector3.new(1, 1, 1) * 200 --4000 -- * 0.000012
bodyGyro.P = 1200
bodyGyro.D = 140 --15

--bodyPosition.P = bodyPosition.P * 1/19
--bodyPosition.D = bodyPosition.D  * 1/19
--bodyGyro.P = bodyGyro.P * 1/19
--bodyGyro.D = bodyGyro.D  * 1/19

local rotateCFrame = CFrame.new()

local weld = Instance.new("Weld", dragPart)

--local interactPermission = require(game.ReplicatedStorage.Interaction.InteractionPermission)
local clientIsDragging = game.ReplicatedStorage.Interaction.ClientIsDragging

local carryAnimationTrack


--------------------------------[[ Drag Main ]]------------------------------------

local draggingPart = false

function click()
	button1Down = true

	local targetObject = game.Players.LocalPlayer:GetMouse().Target
	if not canDrag(targetObject) then
		return
	end
	
	local mouseHit = game.Players.LocalPlayer:GetMouse().Hit.p
	if (mouseHit - Character.Head.Position).magnitude > dragRangeMax then
		return
	end
	
	initializeDrag(targetObject, mouseHit)
	rotateCFrame = CFrame.new()
	
	carryAnimationTrack:Play(0.1, 1, 1)
	
	local dragIsFailing = 0 
	local dragTime = 0
	
	
	while button1Down and canDrag(targetObject) do
		local desiredPos = Character.Head.Position + (game.Players.LocalPlayer:GetMouse().Hit.p - Character.Head.Position).unit * dragRange
		
		local dragRay = Ray.new(Character.Head.Position, desiredPos - Character.Head.Position)
		local part, pos = workspace:FindPartOnRayWithIgnoreList(dragRay, {Character, dragPart, targetObject.Parent})
		
		if part then
			desiredPos = pos
		end
		
		if (camera.CoordinateFrame.p - Character.Head.Position).magnitude > 2 then
			desiredPos = desiredPos + Vector3.new(0, 1.8, 0)
		end
		
		moveDrag(desiredPos)
		bodyGyro.cframe = CFrame.new(dragPart.Position, camera.CoordinateFrame.p) * rotateCFrame
		
		local targParent = findHighestParent(targetObject) or targetObject		
		
		local attemptingToSurf  = false
		for _, check in pairs({{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(0.7, -2.8, 0)).p, Vector3.new(0, -2, 0))}, 
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(0.35, -2.8, 0)).p, Vector3.new(0, -2, 0))}, 
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(0, -2.8, 0)).p, Vector3.new(0, -2, 0))},
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(0.35, -2.8, 0)).p, Vector3.new(0, -2, 0))}, 
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(-0.7, -2.8, 0)).p, Vector3.new(0, -2, 0))}, 
							
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(0.35, -2.8, 0.6)).p, Vector3.new(0, -2, 0))}, 
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(0, -2.8, 0.6)).p, Vector3.new(0, -2, 0))},
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(0.35, -2.8, 0.6)).p, Vector3.new(0, -2, 0))}, 
							
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(0.35, -2.8, -0.6)).p, Vector3.new(0, -2, 0))}, 
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(0, -2.8, -0.6)).p, Vector3.new(0, -2, 0))},
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(0.35, -2.8, -0.6)).p, Vector3.new(0, -2, 0))}, 
							
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(0.5, -0.8, 0)).p, Character.HumanoidRootPart.CFrame.lookVector), State = Enum.HumanoidStateType.Climbing},
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(-0.5, -0.8, 0)).p, Character.HumanoidRootPart.CFrame.lookVector), State = Enum.HumanoidStateType.Climbing},
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(0.5, -1.3, 0)).p, Character.HumanoidRootPart.CFrame.lookVector), State = Enum.HumanoidStateType.Climbing},
							{Ray = Ray.new((Character.HumanoidRootPart.CFrame * CFrame.new(-0.5, -1.3, 0)).p, Character.HumanoidRootPart.CFrame.lookVector), State = Enum.HumanoidStateType.Climbing}
									
					}) do
		
			local ray = check.Ray
			local part, _ = workspace:FindPartOnRayWithIgnoreList(ray, {Character})
			local op = part
			part = part and findHighestParent(part)
			
			if part and (not check.State or Humanoid:GetState() == check.State) then
				if part == targParent then
					attemptingToSurf = true
				else
					for _, connectedPart in pairs(op:GetConnectedParts(true)) do

						if connectedPart == targetObject--[[targParent]] then
							attemptingToSurf = true
							break
						end
					end
				end

				if attemptingToSurf then
					break
				end
			end
		end
		
		
		
		
		
		local falling = Humanoid:GetState() == Enum.HumanoidStateType.Freefall or Humanoid:GetState() == Enum.HumanoidStateType.FallingDown--not part1 and not part2
		
		
		if attemptingToSurf then
			dragIsFailing = 0
		elseif falling then
			dragIsFailing = 0
		elseif (dragPart.Position - desiredPos).magnitude > 5 then
			dragIsFailing = 0
		else
			dragIsFailing = 0
		end
		if dragIsFailing > 16 then
			break
		end
		
		
		if dragTime % 10 == 0 and targParent.Parent:FindFirstChild("BedInfo") and targParent.Parent:FindFirstChild("Main") then
			game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.Parent.Scripts.VehicleControl.SetVehicleOwnership:Fire(targParent.Parent.Main)
		end
		
		clientIsDragging:FireServer(targParent.Parent)
		
		wait()
		dragTime = 0
	end
	
	carryAnimationTrack:Stop()
	
	endDrag()
end


function findHighestParent(child)
	if not child or not child.Parent or child.Parent == workspace then
		return nil
	end
	
	local ret = child.Parent:FindFirstChild("Owner") and child
	return findHighestParent(child.Parent) or ret
end



function clickEnded()
	button1Down = false
end

function holdDistanceChanged()
	dragRange = dragRangeMax--[[_G.dragRangeMin + (1 - dist) * (dragRangeMax - _G.dragRangeMin)]]
end


function canDrag(targetObject)
	
	
	if not (targetObject and not targetObject.Anchored and targetObject.Parent and Humanoid.Health > 0) then -- General conditions
		return false
	end
	
	if targetObject.Name == "LeafPart" then
		return false
	end
	
	local originTargetObject = targetObject
	targetObject = findHighestParent(targetObject) or targetObject
	
	bodyGyro.Parent = dragPart
	
	
	--[[if not (targetObject.Parent:FindFirstChild("Owner") or targetObject.Parent.Parent:FindFirstChild("Owner")) then
		return otherDraggable(targetObject, originTargetObject)
	end]]

	if targetObject.Parent:FindFirstChild("Owner") or targetObject.Parent.Parent:FindFirstChild("Owner") then
		return true
	end
	
	if targetObject.Parent:FindFirstChild("TreeClass") then -- Wood class
		return true
	end
	if targetObject.Parent:FindFirstChild("BoxItemName") then -- Shop items
		return true
	end
	if targetObject.Parent:FindFirstChild("PurchasedBoxItemName") then -- Purchased box items
		return true
	end
	if targetObject.Parent:FindFirstChild("Handle") then -- Tool items
		return true
	end
	
	return otherDraggable(targetObject, originTargetObject)
end

function otherDraggable(targetObject, originTargetObject)
	local draggable = targetObject and targetObject.Parent and targetObject.Parent:FindFirstChild("DraggableItem") or originTargetObject and originTargetObject.Parent and originTargetObject.Parent:FindFirstChild("DraggableItem")
	if draggable then -- Other stuff
		if draggable:FindFirstChild("NoRotate") then
			bodyGyro.Parent  = nil
		end
		return true
	end
end

function initializeDrag(targetObject,mouseHit)
	draggingPart = true
	mouse.TargetFilter = targetObject and findHighestParent(targetObject) and findHighestParent(targetObject).Parent or targetObject

	dragPart.CFrame = CFrame.new(mouseHit, camera.CoordinateFrame.p)

	weld.Part0 = dragPart
	weld.Part1 = targetObject
	weld.C0 =  CFrame.new(mouseHit,camera.CoordinateFrame.p):inverse() * targetObject.CFrame
	weld.Parent = dragPart
	
	dragPart.Parent = workspace
end

function endDrag()
	mouse.TargetFilter = nil
	dragPart.Parent = nil
	draggingPart = false
end

--------------------------------[[ Do Prompt ]]------------------------------------


local dragGuiState = ""
function interactLoop()
	while true do
		wait()
		
		local newState = ""
		
		local mouseHit = game.Players.LocalPlayer:GetMouse().Hit.p
		local targetObject = game.Players.LocalPlayer:GetMouse().Target
		
		
		if draggingPart then
			newState = "Dragging"
		elseif canDrag(targetObject) and not button1Down and (mouseHit - Character.Head.Position).magnitude < dragRangeMax then
			newState = "Mouseover"
		end
		
		if true then-- not (newState == dragGuiState) then
			dragGuiState = newState
			setPlatformControls()
			
			if dragGuiState == "" then
				game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.CanDrag.Visible = false
				game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.CanRotate.Visible = false
			elseif dragGuiState ==  "Mouseover" then
				game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.CanDrag.Visible = true
				game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.CanRotate.Visible = false
			elseif dragGuiState ==  "Dragging" then
				game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.CanDrag.Visible = false
				game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.CanRotate.Visible = not (bodyGyro.Parent == nil) and (not player:FindFirstChild("IsChatting") or player.IsChatting.Value < 1)
			end
		end
		
	end
end


--------------------------------[[ Drag Moving ]]------------------------------------


function moveDrag(pos)
	bodyPosition.position = pos
end
local rotateSpeedReduce = 0.036

local lastRotateTick
function crotate(amount, speed)

	if not draggingPart then
		if not player:FindFirstChild("IsChatting") or player.IsChatting.Value < 2 then
			Humanoid.WalkSpeed = walkSpeed
		end
		return
	end
	
	if Humanoid.WalkSpeed > 1 then
		walkSpeed = Humanoid.WalkSpeed
		Humanoid.WalkSpeed = 0
	end
	
	lastRotateTick = tick()
	local thisRotateTick = lastRotateTick
	
	while draggingPart and amount.magnitude > 0 and lastRotateTick == thisRotateTick do
		rotateCFrame = CFrame.Angles(0, -amount.X * rotateSpeedReduce, 0) * CFrame.Angles(amount.Y * rotateSpeedReduce, 0, 0) * rotateCFrame
		wait()
	end
	
	if amount.magnitude == 0 then
		if not player:FindFirstChild("IsChatting") or  player.IsChatting.Value < 2 then
			Humanoid.WalkSpeed = walkSpeed
		end
	end
end

--------------------------------[[ User Input ]]------------------------------------

wait(1)

carryAnimationTrack = Humanoid:LoadAnimation(game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.Dragger:WaitForChild("CarryItem"))

--input = require(game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.Parent:WaitForChild("Scripts"):WaitForChild("UserInput"))

game.Players.LocalPlayer:GetMouse().Button1Down:connect(function()
	click()
	holdDistanceChanged()
end)
game.Players.LocalPlayer:GetMouse().Button1Up:connect(function()
	clickEnded()
end)
--input.ClickBegan(click, holdDistanceChanged)
--input.ClickEnded(clickEnded)

--input.Rotate(crotate)


function setPlatformControls()
		game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.CanDrag.PlatformButton.Image = game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.CanDrag.PlatformButton.PC.Value
		game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.CanDrag.PlatformButton.KeyLabel.Text = "CLICK"
		game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.CanRotate.PlatformButton.Image = game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.CanRotate.PlatformButton.PC.Value
		game.Players.LocalPlayer.PlayerGui.ItemDraggingGUI.CanRotate.PlatformButton.KeyLabel.Text = "SHIFT + WASD"
end


interactLoop()
end)

tpgift.Name = "tpgift"
tpgift.Parent = scriptframe
tpgift.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
tpgift.BorderSizePixel = 0
tpgift.Position = UDim2.new(0.0720891729, 0, 0.731543601, 0)
tpgift.Size = UDim2.new(0, 101, 0, 19)
tpgift.Font = Enum.Font.Code
tpgift.Text = "TP Gifts"
tpgift.TextColor3 = Color3.new(0, 0.0980392, 1)
tpgift.TextScaled = true
tpgift.TextSize = 25
tpgift.TextWrapped = true
tpgift.MouseButton1Down:connect(function()
for i,v in next,workspace.PlayerModels:GetChildren() do
    if v:FindFirstChild("Main") and v.Owner.Value == game.Players.LocalPlayer then
    for q,p in pairs(v:GetChildren()) do       
        if p.Name:lower():match("box") or p.Name == "DraggableItem" then
            wait()
                v.PrimaryPart = v.Main
                game.ReplicatedStorage.Interaction.Verify:FireServer('Item owned by player',v)
                   v:SetPrimaryPartCFrame(game.Players.LocalPlayer.Character.Head.CFrame)
                 game.ReplicatedStorage.Interaction.ClientIsDragging:FireServer(v)
        end
    end
    end
end
end)

speed.Name = "speed"
speed.Parent = scriptframe
speed.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
speed.BorderSizePixel = 0
speed.Position = UDim2.new(0.53252089, 0, 0.375838965, 0)
speed.Size = UDim2.new(0, 101, 0, 19)
speed.Font = Enum.Font.Code
speed.Text = "100Speed"
speed.TextColor3 = Color3.new(0, 0.0980392, 1)
speed.TextScaled = true
speed.TextSize = 25
speed.TextWrapped = true
speed.MouseButton1Down:connect(function()
while wait()do
service.Players.LocalPlayer.Character.Humanoid.WalkSpeed=Walk 
end 
end)

tpplanks.Name = "tpplanks"
tpplanks.Parent = scriptframe
tpplanks.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
tpplanks.BorderSizePixel = 0
tpplanks.Position = UDim2.new(0.532912374, 0, 0.130872428, 0)
tpplanks.Size = UDim2.new(0, 101, 0, 19)
tpplanks.Font = Enum.Font.Code
tpplanks.Text = "TP Planks"
tpplanks.TextColor3 = Color3.new(0, 0.0980392, 1)
tpplanks.TextScaled = true
tpplanks.TextSize = 25
tpplanks.TextWrapped = true
tpplanks.MouseButton1Down:connect(function()
	for _, Plank in pairs(service.Workspace.PlayerModels:GetChildren()) do
		if Plank.Name == "Plank" and Plank.Owner.Value==service.Players.LocalPlayer then
			Plank:MoveTo(service.Players.LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(0, 20, 0))
				for i=1,100 do
					service.ReplicatedStorage.Interaction.ClientIsDragging:FireServer(Plank)
				end
			end
		end
end)

stopland.Name = "stopland"
stopland.Parent = scriptframe
stopland.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
stopland.BorderSizePixel = 0
stopland.Position = UDim2.new(0.0688835829, 0, 0.375838965, 0)
stopland.Size = UDim2.new(0, 101, 0, 19)
stopland.Font = Enum.Font.Code
stopland.Text = "StopFreeLand"
stopland.TextColor3 = Color3.new(0, 0.0980392, 1)
stopland.TextScaled = true
stopland.TextSize = 25
stopland.TextWrapped = true
stopland.MouseButton1Down:connect(function()
_G.TPStuff = false
while _G.TPStuff == true do
wait(5)
for i,v in pairs(game.Workspace.Properties:GetChildren()) do
    if v.Owner.Value == game.Players.LocalPlayer then
        game.ReplicatedStorage.PropertyPurchasing.ClientExpandedProperty:FireServer(v,CFrame.new(game.Players.LocalPlayer.Character["Left Leg"].Position))
    end
end
end
end)

fly.Name = "fly"
fly.Parent = scriptframe
fly.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
fly.BorderSizePixel = 0
fly.Position = UDim2.new(0.320682108, 0, 0.818791926, 0)
fly.Size = UDim2.new(0, 101, 0, 19)
fly.Font = Enum.Font.Code
fly.Text = "Fly(E)"
fly.TextColor3 = Color3.new(0, 0.0980392, 1)
fly.TextScaled = true
fly.TextSize = 25
fly.TextWrapped = true
fly.MouseButton1Down:connect(function()
 repeat wait()
   until game.Players.LocalPlayer and game.Players.LocalPlayer.Character and game.Players.LocalPlayer.Character:findFirstChild("Torso") and game.Players.LocalPlayer.Character:findFirstChild("Humanoid")
local mouse = game.Players.LocalPlayer:GetMouse()
repeat wait() until mouse
local plr = game.Players.LocalPlayer
local torso = plr.Character.Torso
local flying = true
local deb = true
local ctrl = {f = 0, b = 0, l = 0, r = 0}
local lastctrl = {f = 0, b = 0, l = 0, r = 0}
local maxspeed = 50
local speed = 0

function Fly()
local bg = Instance.new("BodyGyro", torso)
bg.P = 9e4
bg.maxTorque = Vector3.new(9e9, 9e9, 9e9)
bg.cframe = torso.CFrame
local bv = Instance.new("BodyVelocity", torso)
bv.velocity = Vector3.new(0,0.1,0)
bv.maxForce = Vector3.new(9e9, 9e9, 9e9)
repeat wait()
plr.Character.Humanoid.PlatformStand = true
if ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0 then
speed = speed+.5+(speed/maxspeed)
if speed > maxspeed then
speed = maxspeed
end
elseif not (ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0) and speed ~= 0 then
speed = speed-1
if speed < 0 then
speed = 0
end
end
if (ctrl.l + ctrl.r) ~= 0 or (ctrl.f + ctrl.b) ~= 0 then
bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (ctrl.f+ctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(ctrl.l+ctrl.r,(ctrl.f+ctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed
lastctrl = {f = ctrl.f, b = ctrl.b, l = ctrl.l, r = ctrl.r}
elseif (ctrl.l + ctrl.r) == 0 and (ctrl.f + ctrl.b) == 0 and speed ~= 0 then
bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (lastctrl.f+lastctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(lastctrl.l+lastctrl.r,(lastctrl.f+lastctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed
else
bv.velocity = Vector3.new(0,0.1,0)
end
bg.cframe = game.Workspace.CurrentCamera.CoordinateFrame * CFrame.Angles(-math.rad((ctrl.f+ctrl.b)*50*speed/maxspeed),0,0)
until not flying
ctrl = {f = 0, b = 0, l = 0, r = 0}
lastctrl = {f = 0, b = 0, l = 0, r = 0}
speed = 0
bg:Destroy()
bv:Destroy()
plr.Character.Humanoid.PlatformStand = false
end
mouse.KeyDown:connect(function(key)
if key:lower() == "e" then
if flying then flying = false
else
flying = true
Fly()
end
elseif key:lower() == "w" then
ctrl.f = 1
elseif key:lower() == "s" then
ctrl.b = -1
elseif key:lower() == "a" then
ctrl.l = -1
elseif key:lower() == "d" then
ctrl.r = 1
end
end)
mouse.KeyUp:connect(function(key)
if key:lower() == "w" then
ctrl.f = 0
elseif key:lower() == "s" then
ctrl.b = 0
elseif key:lower() == "a" then
ctrl.l = 0
elseif key:lower() == "d" then
ctrl.r = 0
end
end)
Fly()
 
end)

dupe.Name = "dupe"
dupe.Parent = scriptframe
dupe.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
dupe.BorderSizePixel = 0
dupe.Position = UDim2.new(0.536509454, 0, 0.73154366, 0)
dupe.Size = UDim2.new(0, 101, 0, 19)
dupe.Font = Enum.Font.Code
dupe.Text = "Dupe"
dupe.TextColor3 = Color3.new(0, 0.0980392, 1)
dupe.TextScaled = true
dupe.TextSize = 25
dupe.TextWrapped = true
dupe.MouseButton1Down:connect(function()
option = true

a = game.Players.LocalPlayer.CurrentSaveSlot
a.RobloxLocked = option
a.Set.RobloxLocked = option
print(a.Value)

if a.RobloxLocked == true then
print("CurrentSaveSlot RobloxLocked = true, save file won't save")
print("Set RobloxLocked = true, save file won't save")

else

print("CurrentSaveSlot RobloxLocked = false, save file will save")
print("Set RobloxLocked = false, save file will save")
end
end)

stopdupe.Name = "stopdupe"
stopdupe.Parent = scriptframe
stopdupe.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
stopdupe.BorderSizePixel = 0
stopdupe.Position = UDim2.new(0.538308024, 0, 0.6140939, 0)
stopdupe.Size = UDim2.new(0, 101, 0, 19)
stopdupe.Font = Enum.Font.Code
stopdupe.Text = "StopDupe"
stopdupe.TextColor3 = Color3.new(0, 0.0980392, 1)
stopdupe.TextScaled = true
stopdupe.TextSize = 25
stopdupe.TextWrapped = true
stopdupe.MouseButton1Down:connect(function()
option = false

a = game.Players.LocalPlayer.CurrentSaveSlot
a.RobloxLocked = option
a.Set.RobloxLocked = option
print(a.Value)

if a.RobloxLocked == true then
print("CurrentSaveSlot RobloxLocked = true, save file won't save")
print("Set RobloxLocked = true, save file won't save")

else

print("CurrentSaveSlot RobloxLocked = false, save file will save")
print("Set RobloxLocked = false, save file will save")
end
end)

credits.Name = "credits"
credits.Parent = scriptframe
credits.BackgroundColor3 = Color3.new(0.0823529, 0, 1)
credits.BorderSizePixel = 0
credits.Position = UDim2.new(0.133093521, 0, 0.916107357, 0)
credits.Size = UDim2.new(0, 200, 0, 23)
credits.Font = Enum.Font.ArialBold
credits.Text = "Credits: KevinPlayLT2"
credits.TextColor3 = Color3.new(1, 0.866667, 0.109804)
credits.TextScaled = true
credits.TextSize = 14
credits.TextWrapped = true
