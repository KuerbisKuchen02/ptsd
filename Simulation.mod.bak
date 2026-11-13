{10.5.0.3374}
{Enterprise Dynamics startup information}

if(StartingED, SoftStartED([]));


{Model information}

AddLayer([Main], 1, 1, 0);


{Load required atoms}

StoreActiveAtom;
LoadAtomFromFile([Container], pDir([Atoms\BASIC MODELING\Container.atm]));
LoadAtomFromFile([Accumulating Conveyor], pDir([Atoms\TRANSPORT\CONVEYORS\ACCUMULATING\Accumulating Conveyor.atm]));
LoadAtomFromFile([Textbox], pDir([Atoms\VISUALIZATION\Textbox.atm]));
RestoreActiveAtom;


{Atom: Copy of Intersection3In}

sets;
AtomByName([Accumulating Conveyor], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Accumulating Conveyor'. Inheriting from BaseClass.]));
CreateAtom(a, s, [Copy of Intersection3In], 1, false);
SetExprAtt([Speed], [1]);
SetExprAtt([TravelTimeC], [Length / Speed]);
SetAtt([TempMaxLoc], 9);
SetExprAtt([CurLoc], [Min(TempMaxLoc, Speed * (Time - EntryTime(cs)))]);
SetAtt([ExitTime], 0);
SetAtt([CurContent], 0);
SetExprAtt([Length], [If(Elevation <> 0,   Hor_Length / Cos(Angle), Hor_Length)]);
SetExprAtt([SendTo], [{.Min(NrOC(c), NrOC(c) + 1 - IndexMatch(NrOC(c), 1, OCReady(NrOC(c) + 1 - Count, c)))|2. An open channel (First channel first): search, starting from the first channel, and send to the first open channel found..}Min(NrOC(c), NrOC(c) + 1 - IndexMatch(NrOC(c), 1, OCReady(NrOC(c) + 1 - Count, c)))]);
SetAtt([TimeOfEntry], 0);
SetAtt([ExitLength], 1);
SetExprAtt([CalcLocations], [If(Content(c) <> 0,   Do(   TempMaxLoc :=Min(Length, +((Length - ExitLength), (Speed * (Time - ExitTime)))),   ForAtomLayerUnder(c, Do(     Setcs,     SetLoc(-(*(Display_Factor, CurLoc), xSize(cs)), /(-(ySize(c), ySize(cs)), 2), +(zSize(c), *(/(CurLoc, /(If(Use_Physical, xSize(c), Input_Length), xSize(c))), Sin(Angle))), cs),     SetAtt(3, -(TempMaxLoc, ProductSpacing(SpacingRule, xSize(cs), Spacing)), c)    )   )  ) )]);
SetExprAtt([EntryTrigger], [0]);
SetAtt([Capacity], 10000);
SetAtt([SpacingRule], 1);
SetExprAtt([Spacing], [0]);
SetExprAtt([ExitTrigger], [0]);
SetAtt([Use_Physical], 1);
SetAtt([Input_Length], 3);
SetAtt([Display_Factor], 1);
SetAtt([Leg_Supports], 2);
SetExprAtt([Elevation], [0]);
SetExprAtt([Angle], [ArcTan(Elevation / Hor_Length)]);
SetExprAtt([Hor_Length], [If(Use_Physical, xSize(c),    Input_Length)]);
SetAtt([IsConveyor], 5);
SetAtt([Transparency], 0);
SetAtomSettings([], 11249415, 1072);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\conveyor.bmp]), [conveyor]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\AccumulatingConveyor.ico]));
Set(DdbRec, [>legdist:3.]);
SetChannels(1, 1);
SetChannelRanges(1, 255, 1, 255);
SetLoadAtomID(11);
SetChannelRequestCount(1, 0, true, false, 0, 0, [], []);
SetLoc(97, 74, 0);
SetSize(3, 1, 1);
Set(RotationAs, 270);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(13);
ExecLateInit;


{Atom: Copy of Intersection3Out}

sets;
AtomByName([Accumulating Conveyor], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Accumulating Conveyor'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Intersection3Out], 1, false);
SetExprAtt([Speed], [1]);
SetExprAtt([TravelTimeC], [Length / Speed]);
SetAtt([TempMaxLoc], 9);
SetExprAtt([CurLoc], [Min(TempMaxLoc, Speed * (Time - EntryTime(cs)))]);
SetAtt([ExitTime], 0);
SetAtt([CurContent], 0);
SetExprAtt([Length], [If(Elevation <> 0,   Hor_Length / Cos(Angle), Hor_Length)]);
SetExprAtt([SendTo], [{.~1|~1~.}1]);
SetAtt([TimeOfEntry], 0);
SetAtt([ExitLength], 1);
SetExprAtt([CalcLocations], [If(Content(c) <> 0,   Do(   TempMaxLoc :=Min(Length, +((Length - ExitLength), (Speed * (Time - ExitTime)))),   ForAtomLayerUnder(c, Do(     Setcs,     SetLoc(-(*(Display_Factor, CurLoc), xSize(cs)), /(-(ySize(c), ySize(cs)), 2), +(zSize(c), *(/(CurLoc, /(If(Use_Physical, xSize(c), Input_Length), xSize(c))), Sin(Angle))), cs),     SetAtt(3, -(TempMaxLoc, ProductSpacing(SpacingRule, xSize(cs), Spacing)), c)    )   )  ) )]);
SetExprAtt([EntryTrigger], [0]);
SetAtt([Capacity], 10000);
SetAtt([SpacingRule], 1);
SetExprAtt([Spacing], [0]);
SetExprAtt([ExitTrigger], [0]);
SetAtt([Use_Physical], 1);
SetAtt([Input_Length], 3);
SetAtt([Display_Factor], 1);
SetAtt([Leg_Supports], 2);
SetExprAtt([Elevation], [0]);
SetExprAtt([Angle], [ArcTan(Elevation / Hor_Length)]);
SetExprAtt([Hor_Length], [If(Use_Physical, xSize(c),    Input_Length)]);
SetAtt([IsConveyor], 5);
SetAtt([Transparency], 0);
SetAtomSettings([], 11249415, 1072);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\conveyor.bmp]), [conveyor]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\AccumulatingConveyor.ico]));
Set(DdbRec, [>legdist:3.]);
SetChannels(1, 1);
SetChannelRanges(1, 255, 1, 255);
SetLoadAtomID(12);
SetChannelRequestCount(1, 0, true, false, 0, 0, [], []);
SetLoc(96, 71, 0);
SetSize(3, 1, 1);
Set(RotationAs, 90);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(13);
ExecLateInit;


{Atom: Copy of Intersection4In}

sets;
AtomByName([Accumulating Conveyor], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Accumulating Conveyor'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Intersection4In], 1, false);
SetExprAtt([Speed], [1]);
SetExprAtt([TravelTimeC], [Length / Speed]);
SetAtt([TempMaxLoc], 8);
SetExprAtt([CurLoc], [Min(TempMaxLoc, Speed * (Time - EntryTime(cs)))]);
SetAtt([ExitTime], 0);
SetAtt([CurContent], 0);
SetExprAtt([Length], [If(Elevation <> 0,   Hor_Length / Cos(Angle), Hor_Length)]);
SetExprAtt([SendTo], [{.~1|~1~.}1]);
SetAtt([TimeOfEntry], 0);
SetAtt([ExitLength], 1);
SetExprAtt([CalcLocations], [If(Content(c) <> 0,   Do(   TempMaxLoc :=Min(Length, +((Length - ExitLength), (Speed * (Time - ExitTime)))),   ForAtomLayerUnder(c, Do(     Setcs,     SetLoc(-(*(Display_Factor, CurLoc), xSize(cs)), /(-(ySize(c), ySize(cs)), 2), +(zSize(c), *(/(CurLoc, /(If(Use_Physical, xSize(c), Input_Length), xSize(c))), Sin(Angle))), cs),     SetAtt(3, -(TempMaxLoc, ProductSpacing(SpacingRule, xSize(cs), Spacing)), c)    )   )  ) )]);
SetExprAtt([EntryTrigger], [0]);
SetAtt([Capacity], 10000);
SetAtt([SpacingRule], 1);
SetExprAtt([Spacing], [0]);
SetExprAtt([ExitTrigger], [0]);
SetAtt([Use_Physical], 1);
SetAtt([Input_Length], 3);
SetAtt([Display_Factor], 1);
SetAtt([Leg_Supports], 2);
SetExprAtt([Elevation], [0]);
SetExprAtt([Angle], [ArcTan(Elevation / Hor_Length)]);
SetExprAtt([Hor_Length], [If(Use_Physical, xSize(c),    Input_Length)]);
SetAtt([IsConveyor], 5);
SetAtt([Transparency], 0);
SetAtomSettings([], 11249415, 1072);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\conveyor.bmp]), [conveyor]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\AccumulatingConveyor.ico]));
Set(DdbRec, [>legdist:3.]);
SetChannels(1, 1);
SetChannelRanges(1, 255, 1, 255);
SetLoadAtomID(13);
SetChannelRequestCount(1, 0, true, false, 0, 0, [], []);
SetLoc(91, 69, 0);
SetSize(3, 1, 1);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(13);
ExecLateInit;


{Atom: Copy of Intersection4Out}

sets;
AtomByName([Accumulating Conveyor], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Accumulating Conveyor'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Intersection4Out], 1, false);
SetExprAtt([Speed], [1]);
SetExprAtt([TravelTimeC], [Length / Speed]);
SetAtt([TempMaxLoc], 8.99999999999932);
SetExprAtt([CurLoc], [Min(TempMaxLoc, Speed * (Time - EntryTime(cs)))]);
SetAtt([ExitTime], 0);
SetAtt([CurContent], 0);
SetExprAtt([Length], [If(Elevation <> 0,   Hor_Length / Cos(Angle), Hor_Length)]);
SetExprAtt([SendTo], [{.~1|~1~.}1]);
SetAtt([TimeOfEntry], 0);
SetAtt([ExitLength], 1);
SetExprAtt([CalcLocations], [If(Content(c) <> 0,   Do(   TempMaxLoc :=Min(Length, +((Length - ExitLength), (Speed * (Time - ExitTime)))),   ForAtomLayerUnder(c, Do(     Setcs,     SetLoc(-(*(Display_Factor, CurLoc), xSize(cs)), /(-(ySize(c), ySize(cs)), 2), +(zSize(c), *(/(CurLoc, /(If(Use_Physical, xSize(c), Input_Length), xSize(c))), Sin(Angle))), cs),     SetAtt(3, -(TempMaxLoc, ProductSpacing(SpacingRule, xSize(cs), Spacing)), c)    )   )  ) )]);
SetExprAtt([EntryTrigger], [0]);
SetAtt([Capacity], 10000);
SetAtt([SpacingRule], 1);
SetExprAtt([Spacing], [0]);
SetExprAtt([ExitTrigger], [0]);
SetAtt([Use_Physical], 1);
SetAtt([Input_Length], 3);
SetAtt([Display_Factor], 1);
SetAtt([Leg_Supports], 2);
SetExprAtt([Elevation], [0]);
SetExprAtt([Angle], [ArcTan(Elevation / Hor_Length)]);
SetExprAtt([Hor_Length], [If(Use_Physical, xSize(c),    Input_Length)]);
SetAtt([IsConveyor], 5);
SetAtt([Transparency], 0);
SetAtomSettings([], 11249415, 1072);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\conveyor.bmp]), [conveyor]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\AccumulatingConveyor.ico]));
Set(DdbRec, [>legdist:3.]);
SetChannels(1, 1);
SetChannelRanges(1, 255, 1, 255);
SetLoadAtomID(14);
SetChannelRequestCount(1, 0, true, false, 0, 0, [], []);
SetLoc(94, 68, 0);
SetSize(3, 1, 1);
Set(RotationAs, 180);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(13);
ExecLateInit;


{Atom: Copy of Intersection1In}

sets;
AtomByName([Accumulating Conveyor], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Accumulating Conveyor'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Intersection1In], 1, false);
SetExprAtt([Speed], [1]);
SetExprAtt([TravelTimeC], [Length / Speed]);
SetAtt([TempMaxLoc], 7);
SetExprAtt([CurLoc], [Min(TempMaxLoc, Speed * (Time - EntryTime(cs)))]);
SetAtt([ExitTime], 0);
SetAtt([CurContent], 0);
SetExprAtt([Length], [If(Elevation <> 0,   Hor_Length / Cos(Angle), Hor_Length)]);
SetExprAtt([SendTo], [{.~1|~1~.}1]);
SetAtt([TimeOfEntry], 0);
SetAtt([ExitLength], 1);
SetExprAtt([CalcLocations], [If(Content(c) <> 0,   Do(   TempMaxLoc :=Min(Length, +((Length - ExitLength), (Speed * (Time - ExitTime)))),   ForAtomLayerUnder(c, Do(     Setcs,     SetLoc(-(*(Display_Factor, CurLoc), xSize(cs)), /(-(ySize(c), ySize(cs)), 2), +(zSize(c), *(/(CurLoc, /(If(Use_Physical, xSize(c), Input_Length), xSize(c))), Sin(Angle))), cs),     SetAtt(3, -(TempMaxLoc, ProductSpacing(SpacingRule, xSize(cs), Spacing)), c)    )   )  ) )]);
SetExprAtt([EntryTrigger], [0]);
SetAtt([Capacity], 10000);
SetAtt([SpacingRule], 1);
SetExprAtt([Spacing], [0]);
SetExprAtt([ExitTrigger], [0]);
SetAtt([Use_Physical], 1);
SetAtt([Input_Length], 3);
SetAtt([Display_Factor], 1);
SetAtt([Leg_Supports], 2);
SetExprAtt([Elevation], [0]);
SetExprAtt([Angle], [ArcTan(Elevation / Hor_Length)]);
SetExprAtt([Hor_Length], [If(Use_Physical, xSize(c),    Input_Length)]);
SetAtt([IsConveyor], 5);
SetAtt([Transparency], 0);
SetAtomSettings([], 11249415, 1072);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\conveyor.bmp]), [conveyor]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\AccumulatingConveyor.ico]));
Set(DdbRec, [>legdist:3.]);
SetChannels(1, 1);
SetChannelRanges(1, 255, 1, 255);
SetLoadAtomID(15);
SetChannelRequestCount(1, 0, true, false, 0, 0, [], []);
SetLoc(96, 63, 0);
SetSize(3, 1, 1);
Set(RotationAs, 90);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(13);
ExecLateInit;


{Atom: Copy of Intersection1Out}

sets;
AtomByName([Accumulating Conveyor], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Accumulating Conveyor'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Intersection1Out], 1, false);
SetExprAtt([Speed], [1]);
SetExprAtt([TravelTimeC], [Length / Speed]);
SetAtt([TempMaxLoc], 8);
SetExprAtt([CurLoc], [Min(TempMaxLoc, Speed * (Time - EntryTime(cs)))]);
SetAtt([ExitTime], 0);
SetAtt([CurContent], 0);
SetExprAtt([Length], [If(Elevation <> 0,   Hor_Length / Cos(Angle), Hor_Length)]);
SetExprAtt([SendTo], [{.Min(NrOC(c), NrOC(c) + 1 - IndexMatch(NrOC(c), 1, OCReady(NrOC(c) + 1 - Count, c)))|2. An open channel (First channel first): search, starting from the first channel, and send to the first open channel found..}Min(NrOC(c), NrOC(c) + 1 - IndexMatch(NrOC(c), 1, OCReady(NrOC(c) + 1 - Count, c)))]);
SetAtt([TimeOfEntry], 0);
SetAtt([ExitLength], 1);
SetExprAtt([CalcLocations], [If(Content(c) <> 0,   Do(   TempMaxLoc :=Min(Length, +((Length - ExitLength), (Speed * (Time - ExitTime)))),   ForAtomLayerUnder(c, Do(     Setcs,     SetLoc(-(*(Display_Factor, CurLoc), xSize(cs)), /(-(ySize(c), ySize(cs)), 2), +(zSize(c), *(/(CurLoc, /(If(Use_Physical, xSize(c), Input_Length), xSize(c))), Sin(Angle))), cs),     SetAtt(3, -(TempMaxLoc, ProductSpacing(SpacingRule, xSize(cs), Spacing)), c)    )   )  ) )]);
SetExprAtt([EntryTrigger], [0]);
SetAtt([Capacity], 10000);
SetAtt([SpacingRule], 1);
SetExprAtt([Spacing], [0]);
SetExprAtt([ExitTrigger], [0]);
SetAtt([Use_Physical], 1);
SetAtt([Input_Length], 3);
SetAtt([Display_Factor], 1);
SetAtt([Leg_Supports], 2);
SetExprAtt([Elevation], [0]);
SetExprAtt([Angle], [ArcTan(Elevation / Hor_Length)]);
SetExprAtt([Hor_Length], [If(Use_Physical, xSize(c),    Input_Length)]);
SetAtt([IsConveyor], 5);
SetAtt([Transparency], 0);
SetAtomSettings([], 11249415, 1072);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\conveyor.bmp]), [conveyor]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\AccumulatingConveyor.ico]));
Set(DdbRec, [>legdist:3.]);
SetChannels(1, 1);
SetChannelRanges(1, 255, 1, 255);
SetLoadAtomID(16);
SetChannelRequestCount(1, 0, true, false, 0, 0, [], []);
SetLoc(97, 66, 0);
SetSize(3, 1, 1);
Set(RotationAs, 270);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(13);
ExecLateInit;


{Atom: Copy of Intersection2In}

sets;
AtomByName([Accumulating Conveyor], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Accumulating Conveyor'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Intersection2In], 1, false);
SetExprAtt([Speed], [1]);
SetExprAtt([TravelTimeC], [Length / Speed]);
SetAtt([TempMaxLoc], 8);
SetExprAtt([CurLoc], [Min(TempMaxLoc, Speed * (Time - EntryTime(cs)))]);
SetAtt([ExitTime], 0);
SetAtt([CurContent], 0);
SetExprAtt([Length], [If(Elevation <> 0,   Hor_Length / Cos(Angle), Hor_Length)]);
SetExprAtt([SendTo], [{.~1|~1~.}1]);
SetAtt([TimeOfEntry], 0);
SetAtt([ExitLength], 1);
SetExprAtt([CalcLocations], [If(Content(c) <> 0,   Do(   TempMaxLoc :=Min(Length, +((Length - ExitLength), (Speed * (Time - ExitTime)))),   ForAtomLayerUnder(c, Do(     Setcs,     SetLoc(-(*(Display_Factor, CurLoc), xSize(cs)), /(-(ySize(c), ySize(cs)), 2), +(zSize(c), *(/(CurLoc, /(If(Use_Physical, xSize(c), Input_Length), xSize(c))), Sin(Angle))), cs),     SetAtt(3, -(TempMaxLoc, ProductSpacing(SpacingRule, xSize(cs), Spacing)), c)    )   )  ) )]);
SetExprAtt([EntryTrigger], [0]);
SetAtt([Capacity], 10000);
SetAtt([SpacingRule], 1);
SetExprAtt([Spacing], [0]);
SetExprAtt([ExitTrigger], [0]);
SetAtt([Use_Physical], 1);
SetAtt([Input_Length], 3);
SetAtt([Display_Factor], 1);
SetAtt([Leg_Supports], 2);
SetExprAtt([Elevation], [0]);
SetExprAtt([Angle], [ArcTan(Elevation / Hor_Length)]);
SetExprAtt([Hor_Length], [If(Use_Physical, xSize(c),    Input_Length)]);
SetAtt([IsConveyor], 5);
SetAtt([Transparency], 0);
SetAtomSettings([], 11249415, 1072);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\conveyor.bmp]), [conveyor]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\AccumulatingConveyor.ico]));
Set(DdbRec, [>legdist:3.]);
SetChannels(1, 1);
SetChannelRanges(1, 255, 1, 255);
SetLoadAtomID(17);
SetChannelRequestCount(1, 0, true, false, 0, 0, [], []);
SetLoc(102, 68, 0);
SetSize(3, 1, 1);
Set(RotationAs, 180);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(13);
ExecLateInit;


{Atom: Copy of Intersection2Out}

sets;
AtomByName([Accumulating Conveyor], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Accumulating Conveyor'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Intersection2Out], 1, false);
SetExprAtt([Speed], [1]);
SetExprAtt([TravelTimeC], [Length / Speed]);
SetAtt([TempMaxLoc], 8);
SetExprAtt([CurLoc], [Min(TempMaxLoc, Speed * (Time - EntryTime(cs)))]);
SetAtt([ExitTime], 0);
SetAtt([CurContent], 0);
SetExprAtt([Length], [If(Elevation <> 0,   Hor_Length / Cos(Angle), Hor_Length)]);
SetExprAtt([SendTo], [{.~1|~1~.}1]);
SetAtt([TimeOfEntry], 0);
SetAtt([ExitLength], 1);
SetExprAtt([CalcLocations], [If(Content(c) <> 0,   Do(   TempMaxLoc :=Min(Length, +((Length - ExitLength), (Speed * (Time - ExitTime)))),   ForAtomLayerUnder(c, Do(     Setcs,     SetLoc(-(*(Display_Factor, CurLoc), xSize(cs)), /(-(ySize(c), ySize(cs)), 2), +(zSize(c), *(/(CurLoc, /(If(Use_Physical, xSize(c), Input_Length), xSize(c))), Sin(Angle))), cs),     SetAtt(3, -(TempMaxLoc, ProductSpacing(SpacingRule, xSize(cs), Spacing)), c)    )   )  ) )]);
SetExprAtt([EntryTrigger], [0]);
SetAtt([Capacity], 10000);
SetAtt([SpacingRule], 1);
SetExprAtt([Spacing], [0]);
SetExprAtt([ExitTrigger], [0]);
SetAtt([Use_Physical], 1);
SetAtt([Input_Length], 3);
SetAtt([Display_Factor], 1);
SetAtt([Leg_Supports], 2);
SetExprAtt([Elevation], [0]);
SetExprAtt([Angle], [ArcTan(Elevation / Hor_Length)]);
SetExprAtt([Hor_Length], [If(Use_Physical, xSize(c),    Input_Length)]);
SetAtt([IsConveyor], 5);
SetAtt([Transparency], 0);
SetAtomSettings([], 11249415, 1072);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\conveyor.bmp]), [conveyor]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\AccumulatingConveyor.ico]));
Set(DdbRec, [>legdist:3.]);
SetChannels(1, 1);
SetChannelRanges(1, 255, 1, 255);
SetLoadAtomID(18);
SetChannelRequestCount(1, 0, true, false, 0, 0, [], []);
SetLoc(99, 69, 0);
SetSize(3, 1, 1);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(13);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Textbox10 (1) (2)}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Textbox10 (1) (2)], 1, false);
SetTextAtt([Text], [2]);
SetAtt([TextColor], 1);
SetAtt([BackgroundColor], 16777215);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(19);
SetLoc(98, 68, 1);
SetSize(1, 1, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Textbox10 (1) (2) (1)}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Textbox10 (1) (2) (1)], 1, false);
SetTextAtt([Text], [1]);
SetAtt([TextColor], 1);
SetAtt([BackgroundColor], 16777215);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(20);
SetLoc(96, 66, 1);
SetSize(1, 1, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Textbox10 (1)}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Textbox10 (1)], 1, false);
SetTextAtt([Text], [4]);
SetAtt([TextColor], 1);
SetAtt([BackgroundColor], 16777215);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(21);
SetLoc(94, 68, 1);
SetSize(1, 1, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Textbox10 (1) (1)}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Textbox10 (1) (1)], 1, false);
SetTextAtt([Text], [3]);
SetAtt([TextColor], 1);
SetAtt([BackgroundColor], 16777215);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(22);
SetLoc(96, 70, 1);
SetSize(1, 1, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Intersection}

sets;
AtomByName([Accumulating Conveyor], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Accumulating Conveyor'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Intersection], 1, false);
SetExprAtt([Speed], [1]);
SetExprAtt([TravelTimeC], [Length / Speed]);
SetAtt([TempMaxLoc], 0);
SetExprAtt([CurLoc], [Min(TempMaxLoc, Speed * (Time - EntryTime(cs)))]);
SetAtt([ExitTime], 0);
SetAtt([CurContent], 0);
SetExprAtt([Length], [If(Elevation <> 0,   Hor_Length / Cos(Angle), Hor_Length)]);
SetExprAtt([SendTo], [{.~1|~search()~.}search()]);
SetAtt([TimeOfEntry], 0);
SetAtt([ExitLength], 1);
SetExprAtt([CalcLocations], [If(Content(c) <> 0,   Do(   TempMaxLoc :=Min(Length, +((Length - ExitLength), (Speed * (Time - ExitTime)))),   ForAtomLayerUnder(c, Do(     Setcs,     SetLoc(-(*(Display_Factor, CurLoc), xSize(cs)), /(-(ySize(c), ySize(cs)), 2), +(zSize(c), *(/(CurLoc, /(If(Use_Physical, xSize(c), Input_Length), xSize(c))), Sin(Angle))), cs),     SetAtt(3, -(TempMaxLoc, ProductSpacing(SpacingRule, xSize(cs), Spacing)), c)    )   )  ) )]);
SetExprAtt([EntryTrigger], [0]);
SetAtt([Capacity], 10000);
SetAtt([SpacingRule], 1);
SetExprAtt([Spacing], [0]);
SetExprAtt([ExitTrigger], [0]);
SetAtt([Use_Physical], 1);
SetAtt([Input_Length], 1);
SetAtt([Display_Factor], 1);
SetAtt([Leg_Supports], 1);
SetExprAtt([Elevation], [0]);
SetExprAtt([Angle], [ArcTan(Elevation / Hor_Length)]);
SetExprAtt([Hor_Length], [If(Use_Physical, xSize(c),    Input_Length)]);
SetAtt([IsConveyor], 5);
SetAtt([Transparency], 0);
SetAtomSettings([], 11249415, 1072);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\conveyor.bmp]), [conveyor]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\AccumulatingConveyor.ico]));
Set(DdbRec, [>legdist:3.]);
SetChannels(4, 4);
SetChannelRanges(1, 255, 1, 255);
SetLoadAtomID(23);
SetChannelRequestCount(1, 0, true, false, 0, 0, [], []);
SetChannelRequestCount(2, 0, true, false, 0, 0, [], []);
SetChannelRequestCount(3, 0, true, false, 0, 0, [], []);
SetChannelRequestCount(4, 0, true, false, 0, 0, [], []);
SetLoc(96, 68, 0);
SetSize(1, 1, 1);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(13);
ExecLateInit;


{Atom: Container27}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Container27], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8454143, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(24);
SetLoc(104, 48, 0);
SetSize(14, 6, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Container27}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Container27], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(26);
SetLoc(36, -37, 0);
SetSize(23, 51, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Gebäude Text}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Gebäude Text], 1, false);
SetTextAtt([Text], [Gebäude]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8421631);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(27);
SetLoc(44, -12, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Container27}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Container27], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 16764108, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(28);
SetLoc(104, 55, 0);
SetSize(14, 6, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Gewässer Text}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Gewässer Text], 1, false);
SetTextAtt([Text], [Gewässer]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 16765864);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(29);
SetLoc(108, 57, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Container27}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Container27], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 11249415, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(34);
SetLoc(104, 62, 0);
SetSize(14, 7, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Container27 (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Container27 (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(35);
SetLoc(11, 0, 0);
SetSize(18, 14, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Gebäude Text}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Gebäude Text], 1, false);
SetTextAtt([Text], [Gebäude]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8421631);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(36);
SetLoc(17, 6, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Container27}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Container27], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(39);
SetLoc(104, 70, 0);
SetSize(14, 7, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Container27 (2)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Container27 (2)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(40);
SetLoc(12, -86, 0);
SetSize(37, 4, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Gebäude Text (1)}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Gebäude Text (1)], 1, false);
SetTextAtt([Text], [Gebäude]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8421631);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(41);
SetLoc(25, -85, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Container27}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Container27], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(42);
SetLoc(5, -65, 0);
SetSize(44, 17, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Accumulating Conveyor30 (1) (1)}

sets;
AtomByName([Accumulating Conveyor], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Accumulating Conveyor'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Accumulating Conveyor30 (1) (1)], 1, false);
SetExprAtt([Speed], [1]);
SetExprAtt([TravelTimeC], [Length / Speed]);
SetAtt([TempMaxLoc], 0);
SetExprAtt([CurLoc], [Min(TempMaxLoc, Speed * (Time - EntryTime(cs)))]);
SetAtt([ExitTime], 0);
SetAtt([CurContent], 0);
SetExprAtt([Length], [If(Elevation <> 0,   Hor_Length / Cos(Angle), Hor_Length)]);
SetExprAtt([SendTo], [{.~1|~1~.}1]);
SetAtt([TimeOfEntry], 0);
SetAtt([ExitLength], 0);
SetExprAtt([CalcLocations], [If(Content(c) <> 0,   Do(   TempMaxLoc :=Min(Length, +((Length - ExitLength), (Speed * (Time - ExitTime)))),   ForAtomLayerUnder(c, Do(     Setcs,     SetLoc(-(*(Display_Factor, CurLoc), xSize(cs)), /(-(ySize(c), ySize(cs)), 2), +(zSize(c), *(/(CurLoc, /(If(Use_Physical, xSize(c), Input_Length), xSize(c))), Sin(Angle))), cs),     SetAtt(3, -(TempMaxLoc, ProductSpacing(SpacingRule, xSize(cs), Spacing)), c)    )   )  ) )]);
SetExprAtt([EntryTrigger], [0]);
SetAtt([Capacity], 10000);
SetAtt([SpacingRule], 1);
SetExprAtt([Spacing], [0]);
SetExprAtt([ExitTrigger], [0]);
SetAtt([Use_Physical], 1);
SetAtt([Input_Length], 10);
SetAtt([Display_Factor], 1);
SetAtt([Leg_Supports], 4);
SetExprAtt([Elevation], [0]);
SetExprAtt([Angle], [ArcTan(Elevation / Hor_Length)]);
SetExprAtt([Hor_Length], [If(Use_Physical, xSize(c),    Input_Length)]);
SetAtt([IsConveyor], 5);
SetAtt([Transparency], 0);
SetAtomSettings([], 11249415, 1072);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\conveyor.bmp]), [conveyor]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\AccumulatingConveyor.ico]));
Set(DdbRec, [>legdist:3.]);
SetChannels(1, 1);
SetChannelRanges(1, 255, 1, 255);
SetLoadAtomID(45);
SetLoc(91, 58, 0);
SetSize(10, 1, 1);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(13);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Accumulating Conveyor30 (1)}

sets;
AtomByName([Accumulating Conveyor], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Accumulating Conveyor'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Accumulating Conveyor30 (1)], 1, false);
SetExprAtt([Speed], [1]);
SetExprAtt([TravelTimeC], [Length / Speed]);
SetAtt([TempMaxLoc], 0);
SetExprAtt([CurLoc], [Min(TempMaxLoc, Speed * (Time - EntryTime(cs)))]);
SetAtt([ExitTime], 0);
SetAtt([CurContent], 0);
SetExprAtt([Length], [If(Elevation <> 0,   Hor_Length / Cos(Angle), Hor_Length)]);
SetExprAtt([SendTo], [{.~1|~1~.}1]);
SetAtt([TimeOfEntry], 0);
SetAtt([ExitLength], 0);
SetExprAtt([CalcLocations], [If(Content(c) <> 0,   Do(   TempMaxLoc :=Min(Length, +((Length - ExitLength), (Speed * (Time - ExitTime)))),   ForAtomLayerUnder(c, Do(     Setcs,     SetLoc(-(*(Display_Factor, CurLoc), xSize(cs)), /(-(ySize(c), ySize(cs)), 2), +(zSize(c), *(/(CurLoc, /(If(Use_Physical, xSize(c), Input_Length), xSize(c))), Sin(Angle))), cs),     SetAtt(3, -(TempMaxLoc, ProductSpacing(SpacingRule, xSize(cs), Spacing)), c)    )   )  ) )]);
SetExprAtt([EntryTrigger], [0]);
SetAtt([Capacity], 10000);
SetAtt([SpacingRule], 1);
SetExprAtt([Spacing], [0]);
SetExprAtt([ExitTrigger], [0]);
SetAtt([Use_Physical], 1);
SetAtt([Input_Length], 10);
SetAtt([Display_Factor], 1);
SetAtt([Leg_Supports], 4);
SetExprAtt([Elevation], [0]);
SetExprAtt([Angle], [ArcTan(Elevation / Hor_Length)]);
SetExprAtt([Hor_Length], [If(Use_Physical, xSize(c),    Input_Length)]);
SetAtt([IsConveyor], 5);
SetAtt([Transparency], 0);
SetAtomSettings([], 11249415, 1072);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\conveyor.bmp]), [conveyor]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\AccumulatingConveyor.ico]));
Set(DdbRec, [>legdist:3.]);
SetChannels(1, 1);
SetChannelRanges(1, 255, 1, 255);
SetLoadAtomID(46);
SetLoc(101, 57, 0);
SetSize(10, 1, 1);
Set(RotationAs, 180);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(13);
ExecLateInit;


{Atom: Copy of Copy of Accumulating Conveyor30 (1) (1)}

sets;
AtomByName([Accumulating Conveyor], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Accumulating Conveyor'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Accumulating Conveyor30 (1) (1)], 1, false);
SetExprAtt([Speed], [1]);
SetExprAtt([TravelTimeC], [Length / Speed]);
SetAtt([TempMaxLoc], 0);
SetExprAtt([CurLoc], [Min(TempMaxLoc, Speed * (Time - EntryTime(cs)))]);
SetAtt([ExitTime], 0);
SetAtt([CurContent], 0);
SetExprAtt([Length], [If(Elevation <> 0,   Hor_Length / Cos(Angle), Hor_Length)]);
SetExprAtt([SendTo], [{.~1|~1~.}1]);
SetAtt([TimeOfEntry], 0);
SetAtt([ExitLength], 0);
SetExprAtt([CalcLocations], [If(Content(c) <> 0,   Do(   TempMaxLoc :=Min(Length, +((Length - ExitLength), (Speed * (Time - ExitTime)))),   ForAtomLayerUnder(c, Do(     Setcs,     SetLoc(-(*(Display_Factor, CurLoc), xSize(cs)), /(-(ySize(c), ySize(cs)), 2), +(zSize(c), *(/(CurLoc, /(If(Use_Physical, xSize(c), Input_Length), xSize(c))), Sin(Angle))), cs),     SetAtt(3, -(TempMaxLoc, ProductSpacing(SpacingRule, xSize(cs), Spacing)), c)    )   )  ) )]);
SetExprAtt([EntryTrigger], [0]);
SetAtt([Capacity], 10000);
SetAtt([SpacingRule], 1);
SetExprAtt([Spacing], [0]);
SetExprAtt([ExitTrigger], [0]);
SetAtt([Use_Physical], 1);
SetAtt([Input_Length], 10);
SetAtt([Display_Factor], 1);
SetAtt([Leg_Supports], 4);
SetExprAtt([Elevation], [0]);
SetExprAtt([Angle], [ArcTan(Elevation / Hor_Length)]);
SetExprAtt([Hor_Length], [If(Use_Physical, xSize(c),    Input_Length)]);
SetAtt([IsConveyor], 5);
SetAtt([Transparency], 0);
SetAtomSettings([], 11249415, 1072);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\conveyor.bmp]), [conveyor]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\AccumulatingConveyor.ico]));
Set(DdbRec, [>legdist:3.]);
SetChannels(1, 1);
SetChannelRanges(1, 255, 1, 255);
SetLoadAtomID(47);
SetLoc(87, 56, 0);
SetSize(10, 1, 1);
Set(RotationAs, 90);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(13);
ExecLateInit;


{Atom: Copy of Copy of Copy of Accumulating Conveyor30 (2)}

sets;
AtomByName([Accumulating Conveyor], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Accumulating Conveyor'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Accumulating Conveyor30 (2)], 1, false);
SetExprAtt([Speed], [1]);
SetExprAtt([TravelTimeC], [Length / Speed]);
SetAtt([TempMaxLoc], 0);
SetExprAtt([CurLoc], [Min(TempMaxLoc, Speed * (Time - EntryTime(cs)))]);
SetAtt([ExitTime], 0);
SetAtt([CurContent], 0);
SetExprAtt([Length], [If(Elevation <> 0,   Hor_Length / Cos(Angle), Hor_Length)]);
SetExprAtt([SendTo], [{.~1|~1~.}1]);
SetAtt([TimeOfEntry], 0);
SetAtt([ExitLength], 0);
SetExprAtt([CalcLocations], [If(Content(c) <> 0,   Do(   TempMaxLoc :=Min(Length, +((Length - ExitLength), (Speed * (Time - ExitTime)))),   ForAtomLayerUnder(c, Do(     Setcs,     SetLoc(-(*(Display_Factor, CurLoc), xSize(cs)), /(-(ySize(c), ySize(cs)), 2), +(zSize(c), *(/(CurLoc, /(If(Use_Physical, xSize(c), Input_Length), xSize(c))), Sin(Angle))), cs),     SetAtt(3, -(TempMaxLoc, ProductSpacing(SpacingRule, xSize(cs), Spacing)), c)    )   )  ) )]);
SetExprAtt([EntryTrigger], [0]);
SetAtt([Capacity], 10000);
SetAtt([SpacingRule], 1);
SetExprAtt([Spacing], [0]);
SetExprAtt([ExitTrigger], [0]);
SetAtt([Use_Physical], 1);
SetAtt([Input_Length], 10);
SetAtt([Display_Factor], 1);
SetAtt([Leg_Supports], 4);
SetExprAtt([Elevation], [0]);
SetExprAtt([Angle], [ArcTan(Elevation / Hor_Length)]);
SetExprAtt([Hor_Length], [If(Use_Physical, xSize(c),    Input_Length)]);
SetAtt([IsConveyor], 5);
SetAtt([Transparency], 0);
SetAtomSettings([], 11249415, 1072);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\conveyor.bmp]), [conveyor]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\AccumulatingConveyor.ico]));
Set(DdbRec, [>legdist:3.]);
SetChannels(1, 1);
SetChannelRanges(1, 255, 1, 255);
SetLoadAtomID(48);
SetLoc(88, 66, 0);
SetSize(10, 1, 1);
Set(RotationAs, 270);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(13);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Container27 (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Container27 (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(62);
SetLoc(-21, -97, 0);
SetSize(32, 26, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Gebäude Text}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Gebäude Text], 1, false);
SetTextAtt([Text], [Gebäude]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8421631);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(63);
SetLoc(-8, -83, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Container27}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Container27], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(64);
SetLoc(12, -81, 0);
SetSize(37, 16, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Container27 (2)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Container27 (2)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(65);
SetLoc(50, -86, 0);
SetSize(9, 18, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Container27 (2)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Container27 (2)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(66);
SetLoc(50, -57, 0);
SetSize(9, 20, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Container27 (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Container27 (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8454143, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(67);
SetLoc(-24, -59, 0);
SetSize(28, 19, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Attraktion Text}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Attraktion Text], 1, false);
SetTextAtt([Text], [Maus au Chocolat]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8454143);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(68);
SetLoc(-16, -50, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Container27 (1) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Container27 (1) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8454143, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(69);
SetLoc(11, -47, 0);
SetSize(18, 40, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Das verrückte Hote Tartüff}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Das verrückte Hote Tartüff], 1, false);
SetTextAtt([Text], [Das verrückte Hotel Tartüff]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8454143);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(70);
SetLoc(12, -27, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Container27 (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Container27 (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(71);
SetLoc(7, 15, 0);
SetSize(11, 28, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Container27 (1) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Container27 (1) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(72);
SetLoc(21, 46, 0);
SetSize(27, 4, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Container27 (1) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Container27 (1) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(73);
SetLoc(51, 35, 0);
SetSize(8, 8, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Container27 (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Container27 (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(74);
SetLoc(19, 15, 0);
SetSize(31, 23, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Container27 (1) (2)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Container27 (1) (2)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(75);
SetLoc(-16, 33, 0);
SetSize(23, 10, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Container27 (1) (3)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Container27 (1) (3)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(76);
SetLoc(-46, 20, 0);
SetSize(30, 23, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Container27 (2) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Container27 (2) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(77);
SetLoc(66, -86, 0);
SetSize(19, 22, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(78);
SetLoc(49, -67, 0);
SetSize(11, 9, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(79);
SetLoc(30, -38, 0);
SetSize(5, 53, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Container27 (1) (2)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Container27 (1) (2)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8454143, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(80);
SetLoc(-37, -39, 0);
SetSize(47, 53, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Container27 (1) (3)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Container27 (1) (3)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(81);
SetLoc(-51, 0, 0);
SetSize(13, 32, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(82);
SetLoc(-17, -6, 0);
SetSize(47, 5, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Container27 (1) (2)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Container27 (1) (2)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8454143, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(83);
SetLoc(-37, 13, 0);
SetSize(16, 26, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Das verrückte Hote Tartüff}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Das verrückte Hote Tartüff], 1, false);
SetTextAtt([Text], [F.L.Y]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8454143);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(84);
SetLoc(-16, -21, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Container27 (1) (2)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Container27 (1) (2)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(85);
SetLoc(-31, -57, 0);
SetSize(6, 17, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (2)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (2)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(86);
SetLoc(-43, -45, 0);
SetSize(12, 5, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (2)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (2)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(87);
SetLoc(-43, -40, 0);
SetSize(5, 7, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(88);
SetLoc(-29, -65, 0);
SetSize(34, 5, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Container27 (2)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Container27 (2)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(89);
SetLoc(66, -50, 0);
SetSize(17, 8, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(90);
SetLoc(60, -87, 0);
SetSize(5, 44, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(91);
SetLoc(65, -63, 0);
SetSize(27, 12, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(92);
SetLoc(86, -101, 0);
SetSize(6, 38, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Container27 (3)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Container27 (3)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 16764108, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(93);
SetLoc(93, -100, 0);
SetSize(9, 40, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(94);
SetLoc(60, -93, 0);
SetSize(56, 6, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Container27 (3)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Container27 (3)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 16764108, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(95);
SetLoc(102, -100, 0);
SetSize(3, 6, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(96);
SetLoc(86, -108, 0);
SetSize(18, 7, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Container27 (1) (4)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Container27 (1) (4)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(97);
SetLoc(-25, -71, 0);
SetSize(36, 5, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Container27 (3) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Container27 (3) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 16764108, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(98);
SetLoc(102, -79, 0);
SetSize(19, 26, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Container27 (2)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Container27 (2)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8454143, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(99);
SetLoc(25, -72, 0);
SetSize(13, 13, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Attraktion Text}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Attraktion Text], 1, false);
SetTextAtt([Text], [Wellenflug]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8454143);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(100);
SetLoc(28, -66, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Container27 (2) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Container27 (2) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8454143, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(101);
SetLoc(28, 20, 0);
SetSize(13, 13, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Attraktion Text}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Attraktion Text], 1, false);
SetTextAtt([Text], [Pferdekarussell]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8454143);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(102);
SetLoc(30, 26, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Container27 (2)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Container27 (2)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(103);
SetLoc(30, -48, 0);
SetSize(19, 10, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Attraktion Text}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Attraktion Text], 1, false);
SetTextAtt([Text], [Eingang]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8421631);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(104);
SetLoc(32, 47, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Container27 (2) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Container27 (2) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8454143, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(105);
SetLoc(51, 25, 0);
SetSize(8, 9, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Attraktion Text (1)}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Attraktion Text (1)], 1, false);
SetTextAtt([Text], [Bolles Flugschule]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8454143);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(106);
SetLoc(49, 29, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(107);
SetLoc(50, 15, 0);
SetSize(9, 5, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Container27 (2) (1) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Container27 (2) (1) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8454143, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(108);
SetLoc(15, 22, 0);
SetSize(7, 9, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (3)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (3)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(109);
SetLoc(28, 38, 0);
SetSize(13, 8, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Attraktion Text (1)}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Attraktion Text (1)], 1, false);
SetTextAtt([Text], [Bolles Riesenrad]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8454143);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(110);
SetLoc(14, 25, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Container27 (4)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Container27 (4)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 6730675, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(111);
SetLoc(42, 39, 0);
SetSize(8, 6, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Container27 (4)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Container27 (4)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 6730675, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(112);
SetLoc(19, 39, 0);
SetSize(8, 6, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Container27 (4)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Container27 (4)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 6730675, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(113);
SetLoc(51, 21, 0);
SetSize(9, 3, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(114);
SetLoc(-2, -1, 0);
SetSize(3, 14, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(115);
SetLoc(-20, 10, 0);
SetSize(18, 3, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (1) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (1) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(116);
SetLoc(-23, -1, 0);
SetSize(3, 14, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (2)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (2)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(117);
SetLoc(-31, -12, 0);
SetSize(14, 11, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Gebäude Text}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Gebäude Text], 1, false);
SetTextAtt([Text], [Gebäude]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8421631);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(118);
SetLoc(-8, 37, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Gebäude Text (1)}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Gebäude Text (1)], 1, false);
SetTextAtt([Text], [Gebäude]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8421631);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(119);
SetLoc(-37, -43, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Gebäude Text (1)}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Gebäude Text (1)], 1, false);
SetTextAtt([Text], [Gebäude]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8421631);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(120);
SetLoc(52, 38, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Gebäude Text (1)}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Gebäude Text (1)], 1, false);
SetTextAtt([Text], [Gebäude]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8421631);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(121);
SetLoc(72, -46, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Gebäude Text (1)}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Gebäude Text (1)], 1, false);
SetTextAtt([Text], [Gebäude]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8421631);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(122);
SetLoc(71, -76, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Gebäude Text (1)}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Gebäude Text (1)], 1, false);
SetTextAtt([Text], [Gebäude]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 8421631);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(123);
SetLoc(52, -77, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (4)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Copy of Container27 (4)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 6730675, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(124);
SetLoc(60, -34, 0);
SetSize(5, 77, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Gewässer Text}

sets;
AtomByName([Textbox], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Textbox'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Gewässer Text], 1, false);
SetTextAtt([Text], [Gewässer]);
SetAtt([TextColor], 0);
SetAtt([BackgroundColor], 16765864);
SetAtt([FontSize], 1);
SetExprAtt([Font], [4DS[[Arial]]4DS]);
SetAtt([FontScale], 5);
SetAtt([Italic], 0);
SetAtt([Pitch], 0);
SetAtt([xPitch], -45);
SetAtt([zPitch], 0);
SetAtt([3DEnabled], 0);
SetAtt([3DFontSize], 1);
SetAtt([2DEnabled], 1);
SetAtt([TextScript], 0);
SetAtomSettings([], 15, 8224);
Set(Icon(a), 
	RegisterIcon(pDir([media\images\default.jpg]), [default]));
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Textbox.ico]));
SetChannels(1, 0);
SetChannelRanges(1, 1, 0, 0);
SetLoadAtomID(125);
SetLoc(103, -70, 1);
SetSize(6, 2, 0);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Container27 (3)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Container27 (3)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 14143753, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(126);
SetLoc(5, -48, 0);
SetSize(5, 8, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Container27 (1) (2) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Container27 (1) (2) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(127);
SetLoc(-13, 20, 0);
SetSize(5, 13, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;


{Atom: Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (2) (1)}

sets;
AtomByName([Container], Main);
if(not(AtomExists), Error([Cannot find mother atom 'Container'. Inheriting from BaseClass.]));
CreateAtom(a, Up(s), [Copy of Copy of Copy of Copy of Copy of Copy of Container27 (1) (2) (1)], 1, false);
SetAtt([AutoReSize], 0);
SetExprAtt([sx], [1.1]);
SetExprAtt([sy], [1.1]);
SetExprAtt([sz], [1]);
SetAtt([ContainerType], 4);
SetAtt([UseBoxVisible], 1);
SetAtomSettings([], 8421631, 1170);
Set(Icon(a), 
	RegisterIcon(IconsDir([bmp\atoms\Pallet.bmp]), [Pallet.bmp]));
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-wood.wrl]), [pallet-wood.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([pallet-plastic.wrl]), [pallet-plastic.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
AddModel3D(
	RegisterModel3D(Model3DDir([crate.wrl]), [crate.wrl], 0, 0, 0, 1, 1, -1, -90, 0, 0), a);
SetMaterial(
	RegisterMaterial([Default], 8421504, 8421504, 3289650, 0, 0.100000001490116, 0, false, false, 1, 0), 1, a);
Set(Version(a), 0);
SetTreeIcon(pDir([Media\Icons\Container.ico]));
SetLoadAtomID(128);
SetLoc(-13, 15, 0);
SetSize(14, 5, 0.15);
LockPosition(false);
LockSize(false);
DisableIconRotation(false);
SetStatus(0);
ExecLateInit;
Up;
ConnectLoadAtoms(1, 11, 3, 23, 0);
ConnectLoadAtoms(3, 23, 1, 12, 0);
ConnectLoadAtoms(1, 13, 4, 23, 0);
ConnectLoadAtoms(4, 23, 1, 14, 0);
ConnectLoadAtoms(1, 15, 1, 23, 0);
ConnectLoadAtoms(1, 23, 1, 16, 0);
ConnectLoadAtoms(1, 17, 2, 23, 0);
ConnectLoadAtoms(2, 23, 1, 18, 0);


{Experiment settings}

ActivateExperimentAtom;
SetAtt(17, 1);

{Saved Model3D settings.}

ExecOnCreationOnLoad;
