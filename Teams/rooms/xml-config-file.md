---
title: Gestire in remoto le impostazioni del dispositivo Microsoft teams rooms
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
description: Gestione remota delle impostazioni predefinite usate da un dispositivo Microsoft teams rooms, incluso l'applicazione di un tema personalizzato e la creazione di un file di impostazioni master.
ms.openlocfilehash: 77fc064157d57a2584e4a527148a143680010832
ms.sourcegitcommit: 44e47c3b2eb44c38cb8d761befdc6c0cef7c61bc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2020
ms.locfileid: "44842017"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Gestire le impostazioni della console Microsoft teams rooms in remoto con un file di configurazione XML

Questo articolo illustra la gestione remota delle impostazioni predefinite usate da un dispositivo Microsoft teams rooms, incluso l'applicazione di un tema personalizzato. Viene illustrato come creare un file di impostazioni master e i collegamenti alle discussioni su come inserirli in base alle esigenze dei dispositivi gestiti in remoto.
  
È possibile modificare le impostazioni predefinite dei dispositivi gestiti in remoto aggiornando un file XML master e inviando copie alle console gestite. Puoi anche implementare temi personalizzati nelle console delle sale di Microsoft teams con i file di configurazione XML.
  
## <a name="create-an-xml-configuration-file"></a>Creare un file di configurazione XML

Qualsiasi editor di testo può essere usato per creare un file di impostazioni. La tabella **elementi XML** spiega gli elementi illustrati in questo esempio SkypeSettings.xml file di configurazione (nome file obbligatorio).
  
```XML
<SkypeSettings>
    <AutoScreenShare>true</AutoScreenShare>
    <HideMeetingName>true</HideMeetingName>
    <UserAccount>
        <SkypeSignInAddress>RanierConf@contoso.com</SkypeSignInAddress>
        <ExchangeAddress>RanierConf@contoso.com</ExchangeAddress>
        <ModernAuthEnabled>false</ModernAuthEnabled>
        <DomainUsername>Seattle\RanierConf</DomainUsername>
        <Password>password</Password>
        <ConfigureDomain>domain1, domain2</ConfigureDomain>
    </UserAccount>
    <IsTeamsDefaultClient>false</IsTeamsDefaultClient>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>false</AutoAcceptProximateMeetingInvitations>
    <SkypeMeetingsEnabled>false</SkypeMeetingsEnabled>
    <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled>
    <DualScreenMode>true</DualScreenMode>
    <DuplicateIngestDefault>false</DuplicateIngestDefault>
    <SendLogs>
        <EmailAddressForLogsAndFeedback>RanierConf@contoso.com</EmailAddressForLogsAndFeedback>
        <SendLogsAndFeedback>true</SendLogsAndFeedback>
    </SendLogs>
    <Devices>
        <MicrophoneForCommunication>Microsoft LifeChat LX-6000</MicrophoneForCommunication>
        <SpeakerForCommunication>Realtek High Definition Audio</SpeakerForCommunication>
        <DefaultSpeaker>Polycom CX5100</DefaultSpeaker>
        <ContentCameraId>USB\VID_046D&amp;PID_0843&amp;MI_00\7&amp;17446CF2&amp;0&amp;0000</ContentCameraId>
        <ContentCameraInverted>false</ContentCameraInverted>
        <ContentCameraEnhancement>true</ContentCameraEnhancement>
    </Devices>
    <Theming>
        <ThemeName>Custom</ThemeName>
        <CustomThemeImageUrl>file name</CustomThemeImageUrl>
        <CustomThemeColor>
            <RedComponent>100</RedComponent>
            <GreenComponent>100</GreenComponent>
            <BlueComponent>100</BlueComponent>
        </CustomThemeColor>
    </Theming>
</SkypeSettings>
```

Se un valore variabile è di tipo errato, gli elementi non sono in ordine, gli elementi non sono chiusi o viene rilevato un altro errore, il file XML viene *formato male*. Durante l'elaborazione di un file XML formato male, le impostazioni trovate fino al punto in cui si verifica l'errore vengono applicate, quindi il resto del file viene ignorato. Tutti gli elementi sconosciuti nel codice XML vengono ignorati. Se un parametro viene omesso, il dispositivo rimarrà invariato. Se un valore di parametro non è valido, il valore precedente rimane invariato.
  
**Elementi XML**

|Elemento|Tipo|Livello|L'uso|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\> |Contenitore per tutti gli elementi. ||Obbligatorio. |
| \<AutoScreenShare\>  |&#x2777; booleani  |Primo &#x2776;  | Se true, la condivisione schermata automatica è abilitata.  |
|\<HideMeetingName\> |&#x2777; booleani  |Primo &#x2776;  |Se true, i nomi delle riunioni sono nascosti. |
|\<UserAccount\> |Contenitore |Primo &#x2776;  |Contenitore per i parametri delle credenziali. L'indirizzo di accesso, l'indirizzo di Exchange o l'indirizzo di posta elettronica sono in genere gli stessi, ad esempio RanierConf <span></span> @contoso. com. |
|\<SkypeMeetingsEnabled\>  |&#x2777; booleani  |Primo &#x2776;  |Abilitato per impostazione predefinita. |
|\<SkypeSignInAddress\> |&#x2778; di stringa  ||Il nome di accesso per l'account del dispositivo SfB o teams della console. |
|\<ExchangeAddress\> |&#x2778; di stringa  ||Nome di accesso per l'account del dispositivo Exchange della console. Se ExchangeAddress viene omesso, SkypeSignInAddress non verrà riutilizzato automaticamente. |
|\<ModernAuthEnabled> |&#x2777; booleani  |  |Disabilitata per impostazione predefinita. <br/> <br/>Quando è impostato su true, l'applicazione Microsoft teams Rooms usa solo l'autenticazione moderna per la connessione alle risorse e non rientra nell'autenticazione di base.|
|\<DomainUsername\> |&#x2778; di stringa  ||Il dominio e il nome utente del dispositivo console, ad esempio Seattle\RanierConf. |
|\<Password\> |Stringa 3  || Il parametro password è la stessa password usata per l'accesso all'account del dispositivo Skype for business.  |
| \<ConfigureDomain\>  |&#x2778; di stringa  ||È possibile elencare diversi domini, separati da virgole. |
|\<TeamsMeetingsEnabled\> |&#x2777; booleani  |Primo &#x2776;  |Disabilitata per impostazione predefinita. <br/> <br/> Il file XML viene considerato male formato se sia \<SkypeMeetingsEnabled\> e è \<TeamsMeetingsEnabled\> disabilitato, ma è accettabile avere entrambe le impostazioni abilitate in contemporanea. |
|\<IsTeamsDefaultClient> |&#x2777; booleani  |Primo &#x2776;  |Disabilitata per impostazione predefinita. |
|\<BluetoothAdvertisementEnabled> |&#x2777; booleani  |Primo &#x2776;  |Abilitato per impostazione predefinita. |
|\<AutoAcceptProximateMeetingInvitations> |&#x2777; booleani  |Primo &#x2776;  |Se true, le riunioni basate su prossimità vengono accettate automaticamente. Disabilitata per impostazione predefinita. |
|\<DualScreenMode\>  |&#x2777; booleani  |Primo &#x2776;  |Se true, la modalità dual screen è abilitata. In caso contrario, il dispositivo usa la modalità a schermo singolo. |
| \<DuplicateIngestDefault\> |&#x2777; booleani  |Primo &#x2776; |Se true, il contenuto viene visualizzato in entrambe le schermate in modalità dual screen, quando non è presente una riunione. |
|\<DisableTacCommunication\> |&#x2777; booleani  |Primo &#x2776; |Se true, tutte le comunicazioni con gestione dispositivi di amministrazione del team verranno disabilitate. |
|\<SendLogs\> |Contenitore |Primo &#x2776;  |  |
|\<EmailAddressForLogsAndFeedback\> |&#x2778; di stringa  | | Imposta un indirizzo di posta elettronica facoltativo a cui possono essere inviati i log quando viene visualizzata la finestra "Invia feedback". |
|\<SendLogsAndFeedback\> |&#x2777; booleani  | | Se true, i registri vengono inviati all'amministratore. Se false, viene inviato solo il feedback all'amministratore (e non ai registri).  |
| \<Devices\>  |Contenitore |Primo &#x2776;  | I nomi dei dispositivi audio connessi negli elementi figlio corrispondono agli stessi valori elencati nell'app gestione dispositivi. La configurazione può contenere un dispositivo che attualmente non esiste nel sistema, ad esempio un dispositivo A/V non connesso alla console. La configurazione verrebbe mantenuta per il rispettivo dispositivo.  |
|\<MicrophoneForCommunication\> |&#x2778; di stringa  ||Imposta il microfono usato come dispositivo di registrazione in una conferenza. |
|\<SpeakerForCommunication\> |&#x2778; di stringa  ||Dispositivo da usare come altoparlante per la conferenza. Questa impostazione viene usata per impostare il dispositivo altoparlante usato in una chiamata. |
|\<DefaultSpeaker\> |&#x2778; di stringa  ||Dispositivo da usare per riprodurre l'audio da un'origine di ingestione HDMI. |
|\<ContentCameraId>  | &#x2778; di stringa  | | Definire il percorso dell'istanza per la fotocamera configurata in room per condividere il contenuto della lavagna analogica in una riunione. Vedere [individuare il percorso dell'istanza USB di Content camera](#locate-the-content-camera-usb-instance-path).|
|\<ContentCameraInverted>  | &#x2777; booleani | | Specificare se la fotocamera del contenuto è installata fisicamente a testa in giù. Per le fotocamere del contenuto che supportano la rotazione automatica, specificare false. |
|\<ContentCameraEnhancement>  | &#x2777; booleani | |Quando è impostato su true (impostazione predefinita), l'immagine della fotocamera del contenuto è migliorata digitalmente: viene rilevato il bordo della lavagna e viene selezionato uno zoom appropriato, le linee di input penna vengono migliorate e la persona che scrive sulla lavagna viene trasformata in modo trasparente.  <br><br> Impostare su false se si vuole inviare un feed video non elaborato ai partecipanti alla riunione per gli spazi in cui una lavagna non è disegnata con una penna e invece la fotocamera viene usata per mostrare note adesive, poster o altri elementi multimediali.  |
| \<Theming\>  |Contenitore |Primo &#x2776;  |Una delle caratteristiche che è possibile applicare a un file XML è un tema personalizzato per l'organizzazione. È possibile specificare il nome del tema, l'immagine di sfondo e il colore. |
|\<ThemeName\> |&#x2778; di stringa  || Usato per identificare il tema nel client. Le opzioni relative al nome del tema sono predefinite, uno dei temi preimpostati specificati o personalizzati. <br/>  I nomi dei temi personalizzati usano sempre il nome *Custom*. L'interfaccia utente del client può essere impostata alla console per l'impostazione predefinita o uno dei predefiniti, ma l'uso di un tema personalizzato deve essere impostato in remoto da un amministratore. <br/>  I temi preimpostati includono: <br/>  Predefinita <br/>  Onda blu <br/>  Foresta digitale <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel perfetti <br/>  Roadmap <br/>  Tramonto <br/>  Per disabilitare il tema corrente, USA "nessun tema" per il Temaname.  |
|\<CustomThemeImageUrl\> |&#x2778; di stringa  ||Obbligatorio per un tema personalizzato, in caso contrario facoltativo. Immettere solo il nome del file.   |Per altre informazioni sull'immagine del tema personalizzata, vedere la sezione [Immagini tema personalizzate](xml-config-file.md#Themes) .
|\<CustomThemeColor\> |Contenitore ||Contenitore per i \<RedComponent\> \<GreenComponent\> valori, e \<BlueComponent\> . Questi valori sono necessari per un tema personalizzato. |
|\<RedComponent\> |Byte (0-255) ||Rappresenta il componente colore rosso. |
|\<GreenComponent\> |Byte (0-255) ||Rappresenta il componente colore verde. |
|\<BlueComponent\> |Byte (0-255) ||Rappresenta il componente colore blu. | 
| | | |

&#x2776; tutti gli elementi di primo livello sono facoltativi. Se un elemento di primo livello viene omesso, tutti i relativi parametri figlio rimarranno invariati nel dispositivo.
  
&#x2777; un flag booleano può essere: vero, falso, 0 o 1. L'uscita di valori booleani o numerici vuoti può eseguire il rendering di XML non valido e impedire modifiche alle impostazioni.
  
&#x2778; se un parametro stringa è presente e vuoto e Empty è un valore valido, il parametro è deselezionato nel dispositivo.
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>Gestire le impostazioni della console con un file di configurazione XML

All'avvio, se una console Microsoft teams Rooms trova un file XML denominato SkypeSettings.xml in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` cui si trova, applica le impostazioni di configurazione indicate dal file XML e quindi Elimina il file XML.
  
A seconda del numero di dispositivi di Microsoft teams Rooms che l'organizzazione ha e della modalità di gestione per configurarli, esistono diversi modi per inserire il file di configurazione XML. Dopo aver inserito il file nella console, riavviarlo per elaborare le modifiche alla configurazione. Il file di configurazione XML viene eliminato dopo l'elaborazione corretta. I metodi di gestione suggeriti per i dispositivi Microsoft teams Rooms sono discussi in:
  
- [Configurazione dei criteri di gruppo per le sale di Microsoft Teams](rooms-operations.md#GroupPolicy)
- [Gestione remota tramite PowerShell](rooms-operations.md#RemotePS) e [configurare un elemento file](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

Puoi usare qualsiasi metodo che ti piace, purché sia possibile usarlo per trasferire file e attivare un riavvio nel dispositivo console. Il file deve essere leggibile, scrivibile ed Elimina-in grado dall'account utente locale del dispositivo. Preferibilmente è di proprietà di e ha privilegi completi concessi a quell'utente. Se le autorizzazioni per i file non sono impostate correttamente, il software può non riuscire ad applicare le impostazioni, può non riuscire ad eliminare il file dopo l'elaborazione corretta e può addirittura arrestarsi in modo anomalo.
  
## <a name="custom-theme-images"></a>Immagini del tema personalizzate

<a name="Themes"> </a>

Il file di immagine del tema personalizzato deve essere posizionato nella `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` cartella. Immettere il nome e l'estensione del file nella \<CustomThemeImageUrl\> variabile.
  
Il file di immagine deve essere esattamente 3840X1080 pixel e deve essere uno dei formati di file seguenti: jpg, JPEG, PNG e BMP. Se l'organizzazione vuole un'immagine personalizzata, un progettista grafico può usare il [modello tema personalizzato Photoshop](../downloads/ThemingTemplateMicrosoftTeamsRooms_v2.1.psd). Contiene ulteriori dettagli sulla posizione in cui i vari elementi dell'interfaccia utente sono relativi al resto di un'immagine del tema e quali aree vengono visualizzate in console e schermi.
  
Il file di configurazione XML deve essere aggiornato all'avvio del dispositivo per riconoscere l'immagine del tema. Dopo l'elaborazione e l'eliminazione del nuovo file XML, il file dell'elemento grafico del tema viene eliminato dalla directory.
  
## <a name="locate-the-content-camera-usb-instance-path"></a>Individuare il percorso dell'istanza USB di Content camera

Per individuare il percorso dell'istanza:

1. Accedere alle impostazioni di Windows nella console Microsoft teams rooms.
2. Immettere la password di amministratore.
3. Da un prompt dei comandi digitare `devmgmt.msc` per visualizzare Gestione dispositivi.
4. In **Gestione dispositivi**cercare nel nodo **dispositivi di imaging** e individuare la fotocamera del contenuto.
5. Fare clic con il pulsante destro del mouse sulla fotocamera e aprire **Proprietà**.
6. Selezionare la scheda **Dettagli** e individuare la proprietà **percorso istanza dispositivo** nell'elenco a discesa.
7. Il valore visualizzato è il percorso dell'istanza del dispositivo da impostare nel file di configurazione XML. Quando specifichi il percorso in XML, Sostituisci la e commerciale (&) con `&amp;` .

## <a name="see-also"></a>Vedere anche

[Videocamere di contenuto](content-camera.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Configurare un elemento file](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
