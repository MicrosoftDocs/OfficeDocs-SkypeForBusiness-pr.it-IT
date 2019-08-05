---
title: Gestire le impostazioni della console Microsoft teams rooms in remoto con un file di configurazione XML
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection: M365-voice
description: Questo articolo illustra la gestione remota delle impostazioni predefinite usate da un dispositivo Microsoft teams rooms, incluso l'applicazione di un tema personalizzato.
ms.openlocfilehash: 998702a7af98b72139b7f4f20916937ebf7fc247
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182455"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Gestire le impostazioni della console Microsoft teams rooms in remoto con un file di configurazione XML
 
Questo articolo illustra la gestione remota delle impostazioni predefinite usate da un dispositivo Microsoft teams rooms, incluso l'applicazione di un tema personalizzato.
  
L'aggiornamento di un file XML master e l'invio di copie alle console gestite consente di modificare le impostazioni predefinite per i dispositivi gestiti in remoto. Questo articolo illustra come creare un file di questo tipo e i collegamenti alle discussioni su come inserirli in base alle esigenze dei dispositivi gestiti in remoto. Usando questo metodo puoi anche implementare temi personalizzati nelle console delle sale di Microsoft teams. 
  
## <a name="creating-an-xml-configuration-file"></a>Creazione di un file di configurazione XML

Nella tabella seguente vengono illustrati gli elementi illustrati in questo esempio SkypeSettings. XML (questo è un file di configurazione obbligatorio). 
  
```
<SkypeSettings>
  <AutoScreenShare>true</AutoScreenShare>
  <HideMeetingName>true</HideMeetingName>
  <UserAccount>
             <SkypeSignInAddress>RanierConf@contoso.com</SkypeSignInAddress>
             <ExchangeAddress>RanierConf@contoso.com</ExchangeAddress>
             <DomainUsername>Seattle\RanierConf</DomainUsername>
             <Password>password</Password>
             <ConfigureDomain>domain1, domain2</ConfigureDomain>
  </UserAccount>    
  <IsTeamsDefaultClient>false</IsTeamsDefaultClient>
  <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
  <SkypeMeetingsEnabled>false</SkypeMeetingsEnabled> 
  <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled> 
  <DualScreenMode>true</DualScreenMode>
  <SendLogs>                           
             <EmailAddressForLogsAndFeedback>RanierConf@contoso.com</EmailAddressForLogsAndFeedback>
                <SendLogsAndFeedback>true</SendLogsAndFeedback>
  </SendLogs>
  <Devices>
              <MicrophoneForCommunication>Microsoft LifeChat LX-6000</MicrophoneForCommunication>
              <SpeakerForCommunication>Realtek High Definition Audio</SpeakerForCommunication>
              <DefaultSpeaker>Polycom CX5100</DefaultSpeaker>
  </Devices>
  <Theming> 
    <ThemeName>Custom</ThemeName>
       <CustomThemeImageUrl>folder path</CustomThemeImageUrl>
      <CustomThemeColor>
           <RedComponent>100</RedComponent>
           <GreenComponent>100</GreenComponent>
           <BlueComponent>100</BlueComponent>
         </CustomThemeColor>
  </Theming>
</SkypeSettings>
```

Se il file XML viene formattato in modo errato, ovvero se un valore variabile è di tipo sbagliato, gli elementi non sono in ordine, gli elementi vengono chiusi e così via, le impostazioni trovate fino al punto in cui viene trovato l'errore vengono applicate, quindi il resto del file viene ignorato durante l'elaborazione. Tutti gli elementi sconosciuti nel codice XML vengono ignorati. Se un parametro viene omesso, il dispositivo rimarrà invariato. Se il valore di un parametro non è valido, il valore precedente rimane invariato.
  
**Elementi XML**
 
|Elemento|Tipo|Livello|L'uso|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\>   |Contenitore per tutti gli elementi.   ||Obbligatorio.   |
| \<AutoScreenShare\>  |&#x2777; booleani  |Primo &#x2776;  | Se true, la condivisione schermata automatica è abilitata.  |
|\<HideMeetingName\>   |&#x2777; booleani  |Primo &#x2776;  |Se true, i nomi delle riunioni sono nascosti.   |
|\<UserAccount\>   |Contenitore   |Primo &#x2776;  |Contenitore per i parametri delle credenziali.   L'indirizzo di accesso, l'indirizzo di Exchange o l'indirizzo di posta elettronica sono in genere gli<span></span>stessi, ad esempio RanierConf @contoso. com.   |
|\<SkypeMeetingsEnabled\>  |&#x2777; booleani  |Primo &#x2776;  |Abilitato per impostazione predefinita.   |
|\<SkypeSignInAddress\>   |&#x2778; di stringa  ||Il nome di accesso per l'account del dispositivo Skype for business della console.   |
|\<ExchangeAddress\>   |&#x2778; di stringa  ||Nome di accesso per l'account del dispositivo Exchange della console.   Se ExchangeAddress viene omesso, SkypeSignInAddress non verrà riusato automaticamente.   |
|\<DomainUsername\>   |&#x2778; di stringa  ||Il dominio e il nome utente del dispositivo console, ad esempio Seattle\RanierConf.   |
|\<Password\>   |Stringa 3  || Il parametro password è la stessa password usata per l'accesso all'account del dispositivo Skype for business.  |
| \<ConfigureDomain\>  |&#x2778; di stringa  ||È possibile elencare diversi domini, separati da virgole.   |
|\<TeamsMeetingsEnabled\>   |&#x2777; booleani  |Primo &#x2776;  |Disabilitata per impostazione predefinita. <br/> <br/> Il file XML viene considerato male formato se sia \<SkypeMeetingsEnabled\> che\<TeamsMeetingsEnabled\> sono disabilitati, ma è accettabile che entrambe le impostazioni siano abilitate in contemporanea.   |
|\<> IsTeamsDefaultClient |&#x2777; booleani  |Primo &#x2776;  |Disabilitata per impostazione predefinita. |
|\<> BluetoothAdvertisementEnabled |&#x2777; booleani  |Primo &#x2776;  |Abilitato per impostazione predefinita. |
|\<DualScreenMode\>  |&#x2777; booleani  |Primo &#x2776;  |Se true, la modalità dual screen è abilitata. In caso contrario, il dispositivo userà la modalità a schermo singolo.   |
|\<SendLogs\>   |Contenitore   |Primo &#x2776;  ||
|\<EmailAddressForLogsAndFeedback\>   |&#x2778; di stringa  ||Questo imposta un indirizzo di posta elettronica facoltativo a cui possono essere inviati i log quando viene visualizzata la finestra "Invia feedback".   |
|\<SendLogsAndFeedback\>   |&#x2777; booleani  || Se true, i registri vengono inviati all'amministratore. Se false, viene inviato solo il feedback all'amministratore (e non ai registri).  |
| \<Dispositivi\>  |Contenitore   |Primo &#x2776;  | I nomi dei dispositivi audio connessi negli elementi figlio corrispondono agli stessi valori elencati nell'app gestione dispositivi. La configurazione può contenere un dispositivo che attualmente non esiste nel sistema, ad esempio un dispositivo A/V non connesso alla console. La configurazione verrebbe mantenuta per il rispettivo dispositivo.  |
|\<MicrophoneForCommunication\>   |&#x2778; di stringa  ||Imposta il microfono che verrà usato come dispositivo di registrazione in una conferenza.   |
|\<SpeakerForCommunication\>   |&#x2778; di stringa  ||Dispositivo da usare come altoparlante per la conferenza. Questa impostazione viene usata per impostare il dispositivo altoparlante che verrà usato per ascoltare l'audio in una chiamata.   |
|\<DefaultSpeaker\>   |&#x2778; di stringa  ||Dispositivo da usare per riprodurre l'audio da un'origine di ingestione HDMI.   |
| \<Temi\>  |Contenitore   |Primo &#x2776;  |Una delle caratteristiche che possono essere applicate usando un file XML è un tema personalizzato per l'organizzazione. Sarà possibile specificare un nome del tema, un'immagine di sfondo e un colore.   |
|\<ThemeName\>   |&#x2778; di stringa  || Usato per identificare il tema nel client. Le opzioni relative al nome del tema sono predefinite, uno dei temi preimpostati specificati o personalizzati. <br/>  I nomi dei temi personalizzati devono sempre usare il nome *Custom* . L'interfaccia utente del client può essere impostata alla console per l'impostazione predefinita o uno dei predefiniti, ma l'applicazione di un tema personalizzato deve essere impostata in remoto da un amministratore. <br/>  I temi preimpostati includono: <br/>  Predefinita <br/>  Onda blu <br/>  Foresta digitale <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel perfetti <br/>  Roadmap <br/>  Tramonto <br/>  Per disabilitare il tema corrente, USA "nessun tema" per il Temaname.  |
|\<CustomThemeImageUrl\>   |&#x2778; di stringa  ||Obbligatorio se si usa un tema personalizzato, in caso contrario facoltativo. Per altre informazioni sull'immagine del tema personalizzato, vedere la sezione [Immagini tema personalizzate](xml-config-file.md#Themes) .  |
|\<CustomThemeColor\>   |Contenitore   ||Contenitore per i \<valori\>di \<RedComponent\>, GreenComponent \<e\> BlueComponent. Questi valori sono obbligatori se si usa un tema personalizzato.   |
|\<RedComponent\>   |Byte (0-255)   ||Rappresenta il componente colore rosso.   |
|\<GreenComponent\>   |Byte (0-255)   ||Rappresenta il componente colore verde.   |
|\<BlueComponent\>   |Byte (0-255)   ||Rappresenta il componente colore blu.   |
| | | |
   
&#x2776; tutti gli elementi di primo livello sono facoltativi. Se un elemento di primo livello viene omesso, tutti i relativi parametri figlio rimarranno invariati nel dispositivo.
  
&#x2777; un flag Boolean può essere uno degli elementi seguenti: vero, falso, 0 o 1. I valori booleani o numerici a sinistra vuoti potrebbero eseguire il rendering di XML non valido in modo che non vengano apportate modifiche alle impostazioni.
  
 &#x2778; se un parametro di stringa è presente, Empty e Empty è un valore valido, il parametro è deselezionato nel dispositivo.
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>Gestire le impostazioni della console usando un file di configurazione XML

All'avvio, se una console Microsoft teams Rooms trova un file XML denominato SkypeSettings. XML nella posizione **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, le impostazioni di configurazione verranno applicate indicato dal file XML, quindi eliminare il file XML.
  
A seconda del numero di dispositivi Microsoft teams Rooms che l'azienda ha e di come si sceglie di gestire per configurarli, è possibile inserire il file di configurazione XML in diversi modi. Dopo aver inserito il file nella console, riavviarlo per elaborare le modifiche alla configurazione. Il file di configurazione XML viene eliminato dopo l'elaborazione corretta. I metodi di gestione suggeriti per i dispositivi Microsoft teams Rooms sono discussi in:
  
- [Configurazione dei criteri di gruppo per le sale di Microsoft Teams](room-systems-v2-operations.md#GroupPolicy)
    
- [Gestione remota tramite PowerShell](room-systems-v2-operations.md#RemotePS) e [configurare un elemento file](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
    
Puoi usare qualsiasi metodo che ti piace, purché sia possibile usarlo per trasferire file e attivare un riavvio nel dispositivo console. Il file deve essere leggibile, scrivibile ed Elimina-in grado dall'account utente locale del dispositivo (preferibilmente dovrebbe essere di proprietà e avere i privilegi completi concessi a tale utente). Se le autorizzazioni per i file non sono impostate correttamente, il software potrebbe non riuscire ad applicare le impostazioni, potrebbe non riuscire ad eliminare il file dopo l'elaborazione corretta e potrebbe addirittura arrestarsi in modo anomalo.
  
## <a name="custom-theme-images"></a>Immagini del tema personalizzate
<a name="Themes"> </a>

Il file di immagine del tema personalizzato deve essere inserito in **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, basta immettere il nome e l'estensione \<del\> file nella variabile CustomThemeImageUrl.
  
Il file di immagine deve essere esattamente 3840X1080 pixel e deve essere uno dei formati di file seguenti: jpg, JPEG, PNG e BMP. Se l'organizzazione vuole un'immagine personalizzata, un progettista grafico troverà utile il [modello di Photoshop per il tema personalizzato](https://go.microsoft.com/fwlink/?linkid=870441) . Contiene ulteriori dettagli su dove inserire vari elementi in un'immagine del tema e quali aree vengono visualizzate in console e schermi.
  
Il file di configurazione XML deve essere aggiornato all'avvio del dispositivo per riconoscere l'immagine del tema. Dopo l'elaborazione e l'eliminazione del nuovo file XML, il file dell'elemento grafico del tema verrà eliminato dalla directory.
  
## <a name="see-also"></a>Vedere anche


[Gestire le sale di Microsoft Teams](skype-room-systems-v2.md)

[Configurare un elemento file](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
