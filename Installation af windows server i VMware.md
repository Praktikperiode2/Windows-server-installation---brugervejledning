<div style="text-align: center;">
    <img src="media/image1.png" width="312" height="232" />


</div>

> **Installation af Windows 2016/2019 server i en Vmware client**



> indtast i en Chrome browser og klik på avanceret og Forsæt til
192.168.4.12

<div style="text-align: center;">
    <img src="media/image2.png" width="586" height="299" alt="Beskrivelse" />
</div>

> Klik på "LAUNCH VSPHERE CLIENT (HTML 5)"

<div style="text-align: center;">
    <img src="media/image3.png" width="476" height="342" alt="Beskrivelse" />
</div>

> Indtast dit bruger navn og password til elevnettet og derefter på login.

<div style="text-align: center;">
    <img src="media/image4.png" width="470" height="252" alt="Beskrivelse" />
</div>

> I VMWARE vSphere Web Clienten kan den virtuelle maskine nu konfigureres og der kan installeres et gæste operativ system på den.

<div style="text-align: center;">
    <img src="media/image5.png" width="658" height="399" alt="Beskrivelse" />
</div>

> Installation af gæste operativ system gøres på følgende måde:
> Start den virtuelle maskine ved at klikke på "Launch Remote Console":

<div style="text-align: center;">
    <img src="media/image6.png" width="658" height="378" alt="Beskrivelse" />
</div>

> I det nye browser vindue er der en dialog box for aktivering af VMRC protokollen. Klik på "Open Vmware Remote Console

<div style="text-align: center;">
    <img src="media/image7.png" width="401" height="147" alt="Beskrivelse" />
</div>

Der er nu et Vmware Remote Console vindue med en fejlbesked. Klik på "connect anyway".

<div style="text-align: center;">
    <img src="media/image8.png" width="329" height="156" alt="Beskrivelse" />
</div>

Start den virtuelle maskine:

<div style="text-align: center;">
    <img src="media/image9.png" width="199" height="105" alt="Beskrivelse" />
</div>

I console vinduet skal ISO filen med operativ systemet nu tilknyttes til et virtuelt Cdrom drev (højre klik på CD-ROM symbolet):

<div style="text-align: center;">
    <img src="media/image10.png" width="597" height="132" alt="Beskrivelse" />
</div>

Vælg Windows server 2016/2019 ISO filen i stifinderen. Klik på "Open" Genstart den virtuelle maskine:

<div style="text-align: center;">
    <img src="media/image11.png" width="261" height="154" alt="Beskrivelse" />
</div>

Umiddelbar efter genstarten klikkes der i vinduet med musen og derefter på Escape knappen.

<div style="text-align: center;">
    <img src="media/image12.png" width="226" height="136" alt="Beskrivelse" />
</div>

Vælg 3. CD-rom Drive:

Installationen af Windows server starter op automatisk.

<div style="text-align: center;">
    <img src="media/image13.png" width="435" height="320" alt="Beskrivelse" />
</div>

Vælg dansk "Time and currency format" og "Keyboard". Klik på "Next" og derefter "Install now". I Windows setup vælg "Windows server 2016/2019 Standard Evaluation" og derefter "Next".

<div style="text-align: center;">
    <img src="media/image14.png" width="452" height="337" alt="Beskrivelse" />
</div>

Accepter licens betingelserne og derefter klik "Next"..

<div style="text-align: center;">
    <img src="media/image15.png" width="302" height="229" alt="Beskrivelse" />
</div>

Klik på install:\
Mangler et sceen dump\
Installationen kører nu og status kan følges i nedenstående vindue:

<div style="text-align: center;">
    <img src="media/image16.png" width="386" height="159" alt="Beskrivelse" />
</div>

Opret en administrator account. Klik "Finish".

<div style="text-align: center;">
    <img src="media/image17.png" width="456" height="372" alt="Beskrivelse" />
</div>

Den virtuelle Windows 2016/2019 server er nu installeret:

<div style="text-align: center;">
    <img src="media/image18.png" width="555" height="447" alt="Beskrivelse" />
</div>

Login på serveren. Klik på "VMRC" og derefter på "Send Ctrl+Alt+Del".

<div style="text-align: center;">
    <img src="media/image19.png" width="247" height="239" alt="Beskrivelse" />
</div>

Log på som administrator.

<div style="text-align: center;">
    <img src="media/image20.png" width="455" height="371" alt="Beskrivelse" />
</div>

Opsætning af netværk. Find "Network and Sharing Center".

<div style="text-align: center;">
    <img src="media/image21.png" width="627" height="286" alt="Beskrivelse" />
</div>

Klik på "Change adapter settings". Dobbelt klik på "Ethernet0". I Dialogen "Ethernet0 Status" klik på "Properties".

<div style="text-align: center;">
    <img src="media/image22.png" width="444" height="424" alt="Beskrivelse" />
</div>

Vælg "Internet Protocol Version 4" og derefter "Properties".

<div style="text-align: center;">
    <img src="media/image23.png" width="324" height="415" alt="Beskrivelse" />
</div>

Indtast nedenstående informationer: OBS IP Address, Subnet mask og gateway får du af instruktøren.

<div style="text-align: center;">
    <img src="media/image24.png" width="399" height="456" alt="Beskrivelse" />
</div>

Klik på "OK" for at afslutte netværkskonfigurationen.
