---
title: Sicurezza delle sale di Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Informazioni su come proteggere i dispositivi di Microsoft Teams Rooms.
ms.openlocfilehash: 522cc845e2e6b8b1f57fc0ab1c1523452ec429f8
ms.sourcegitcommit: 6785d7f1ef5d2010ab334ec8cc46884327a53662
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2021
ms.locfileid: "50395378"
---
# <a name="microsoft-teams-rooms-security"></a>Sicurezza delle sale di Microsoft Teams

Microsoft collabora con i nostri partner per fornire una soluzione sicura che non richieda azioni aggiuntive per proteggere le sale di Microsoft Teams. Questo articolo illustra molte delle funzionalità di sicurezza disponibili in Teams Room.

> [!NOTE]
> Le sale di Microsoft Teams non devono essere trattate come una tipica workstation di utenti finali. Non solo i casi di utilizzo sono molto diversi, ma anche i profili di sicurezza predefiniti sono molto diversi.

I dati per gli utenti finali limitati vengono archiviati nelle sale di Teams. I dati degli utenti finali possono essere archiviati nei file di log solo per la risoluzione dei problemi e il supporto. In nessun momento un partecipante a una riunione con Teams Room può copiare i file nel disco rigido o accedere come se stessi. Nessun dato dell'utente finale viene trasferito o accessibile dal dispositivo Sale di Microsoft Teams.

Anche se gli utenti finali non possono inserire file in un disco rigido di Teams Room, Microsoft Defender è ancora abilitato. Le prestazioni di Teams Rooms vengono testate con Microsoft Defender. La disabilitazione o l'aggiunta di software di sicurezza dell'endpoint può portare a risultati imprevisti e a una possibile riduzione del sistema.

## <a name="hardware-security"></a>Sicurezza hardware

In un ambiente Teams Rooms è presente un modulo di elaborazione centrale che esegue Windows 10 IoT Enterprise Edition. Ogni modulo di elaborazione certificato deve avere una soluzione di montaggio sicura, uno slot di blocco di sicurezza (ad esempio, Blocco Kensington) e misure di sicurezza per l'accesso alle porte I/O per impedire la connessione di dispositivi non autorizzati. È anche possibile disabilitare porte specifiche tramite la configurazione UEFI (Unified Extensible Firmware Interface).

Ogni modulo di elaborazione certificato deve essere spedito con la tecnologia di conformità Trusted Platform Module (TPM) 2.0 abilitata per impostazione predefinita. TPM viene usato per crittografare le informazioni di accesso per l'account della risorsa Teams Rooms.

L'avvio sicuro è abilitato per impostazione predefinita. L'avvio sicuro è uno standard di sicurezza sviluppato dai membri del settore PC per garantire che il dispositivo sia in uso solo con software attendibile dal produttore OEM (Original Equipment Manufacturer). All'avvio del PC, il firmware controlla la firma di ogni parte del software di avvio, inclusi i driver del firmware UEFI (noti anche come ROMS option), le applicazioni EFI e il sistema operativo. Se le firme sono valide, il PC si avvia e il firmware cede il controllo al sistema operativo. Per altre informazioni, vedere [Avvio sicuro.](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

L'accesso alle impostazioni UEFI è possibile solo collegando una tastiera e un mouse fisici. Ciò impedisce l'accesso alla UEFI tramite la console abilitata per il tocco di Teams Rooms e qualsiasi altro schermo abilitato per il tocco collegato alle sale di Teams.

La protezione DMA (Direct Memory Access) kernel è un'impostazione di Windows 10 abilitata nelle sale di Teams. Con questa funzionalità, il sistema operativo e il firmware del sistema proteggono il sistema da attacchi DMA dannosi e indesiderati per tutti i dispositivi che supportano DMA:

- Durante il processo di avvio.

- Per danni a DMA dannosi da parte di dispositivi connessi a porte interne/esterne che supportano DMA facilmente accessibili, come slot M.2 PCIe e Thunderbolt 3, durante il runtime del sistema operativo.

Teams Rooms abilita anche l'integrità del codice protetto da Hypervisor (HVCI). Una delle funzionalità fornite da HVCI è Credential Guard. Credential Guard offre i vantaggi seguenti:

- **Sicurezza hardware** NTLM, Kerberos e Gestione credenziali sfruttano le funzionalità di sicurezza della piattaforma, tra cui avvio sicuro e virtualizzazione, per proteggere le credenziali.

- **Sicurezza basata sulla virtualizzazione** Le credenziali derivate Windows NTLM e Kerberos e altri segreti vengono eseguiti in un ambiente protetto isolato dal sistema operativo in esecuzione.

- **Maggiore protezione da minacce persistenti avanzate** Quando le credenziali di dominio di Gestione credenziali, NTLM e le credenziali derivate Kerberos sono protette con la sicurezza basata sulla virtualizzazione, le tecniche di attacco di furto delle credenziali e gli strumenti usati in molti attacchi mirati vengono bloccati. Il malware in esecuzione nel sistema operativo con privilegi amministrativi non può estrarre segreti protetti dalla sicurezza basata sulla virtualizzazione.

## <a name="software-security"></a>Sicurezza software

Dopo l'avvio di Microsoft Windows, La chat room di Teams accede automaticamente a un account utente di Windows locale denominato Skype. L'account Skype non ha una password. Per rendere sicura la sessione dell'account Skype, seguire questa procedura.

> [!IMPORTANT]
> Non modificare la password o modificare l'account utente Skype locale. In questo modo è possibile impedire l'accesso automatico alle sale di Teams.

L'app Sale di Microsoft Teams viene eseguita con la funzionalità Accesso assegnato disponibile in Windows 10 1903 e versioni successive. Accesso assegnato è una caratteristica di Windows 10 che limita i punti di ingresso dell'applicazione esposti all'utente. Questo è ciò che consente la modalità chiosco multimediale per singola app. Con Shell Launcher, le sale di Teams sono configurate come un dispositivo chiosco multimediale che esegue un'applicazione desktop di Windows come interfaccia utente. L'app Sale di Microsoft Teams sostituisce la shell predefinita (explorer.exe) che viene in genere eseguita quando un utente esegue l'accesso. In altre parole, la shell tradizionale di Explorer non viene avviata. Questo riduce notevolmente la vulnerabilità delle sale di Microsoft Teams all'interno di Windows. Per altre informazioni, vedere [Configurare chioschi e segnali digitali nelle edizioni desktop di Windows.](https://docs.microsoft.com/windows/configuration/kiosk-methods)

Se decidi di eseguire un'analisi della sicurezza o un benchmark CIS (Center for Internet Security) su Teams Rooms, l'analisi può essere eseguita solo nel contesto di un account amministratore locale perché l'account utente Skype non supporta l'esecuzione di applicazioni diverse dall'app Teams Rooms. Molte delle funzionalità di sicurezza applicate al contesto dell'utente Skype non si applicano ad altri utenti locali e, di conseguenza, queste scansioni di sicurezza non esererà il blocco completo della sicurezza applicato all'account Skype. Di conseguenza, non è consigliabile eseguire un'analisi locale nelle sale di Teams. Tuttavia, se si desidera, è possibile eseguire test di interni esterni. Per questo, è consigliabile eseguire test di funzionamento esterni sui dispositivi di Teams Room invece di eseguire scansioni locali.

Inoltre, i criteri di blocco vengono applicati per limitare l'uso delle caratteristiche non amministrative. Un filtro da tastiera è abilitato per intercettare e bloccare combinazioni di tasti potenzialmente non sicure non coperte dai criteri di accesso assegnato. Solo gli utenti con diritti amministrativi locali o di dominio possono accedere a Windows per gestire le sale di Teams. Questi e altri criteri applicati a Windows nei dispositivi Microsoft Teams Room vengono continuamente valutati e testati durante il ciclo di vita del prodotto.

## <a name="account-security"></a>Sicurezza dell'account

I dispositivi di Teams Rooms includono un account amministrativo denominato "Amministratore" con una password predefinita. È consigliabile cambiare la password predefinita il più presto possibile dopo aver completato la configurazione.

L'account amministratore non è necessario per il corretto funzionamento dei dispositivi di Teams Room e può essere rinominato o persino eliminato. Tuttavia, prima di eliminare l'account amministratore, assicurarsi di configurare un account di amministratore locale alternativo configurato prima di rimuovere quello fornito con i dispositivi di Teams Rooms. Per altre informazioni su come cambiare la password di un account Windows locale usando gli strumenti predefiniti di Windows o PowerShell, vedere le risorse seguenti:

- [Cambiare o reimpostare la password di Windows](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

È anche possibile importare account di dominio nel gruppo di amministratori di Windows locale. È possibile eseguire questa operazione per gli account di Azure AD usando Intune. Per altre informazioni, vedere [Policy CSP - RestrictedGroups.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!CAUTION]
> Se si elimina o si disabilita l'account Amministratore prima di concedere le autorizzazioni di amministratore locale a un altro account locale o di dominio, si potrebbe perdere la possibilità di amministrare il dispositivo Sale di Teams. In questo caso, è necessario ripristinare le impostazioni originali del dispositivo e completare di nuovo il processo di configurazione.
>
> Non concedere autorizzazioni di amministratore locale all'account utente Skype.

Progettazione configurazione di Windows può essere usato per creare pacchetti di provisioning di Windows 10. Oltre a cambiare la password di amministratore locale, puoi anche eseguire operazioni come modificare il nome del computer e registrarti in Azure Active Directory. Per altre informazioni sulla creazione di un pacchetto di provisioning di Progettazione configurazione di Windows, vedi [Provisioning dei pacchetti per Windows 10.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)

È necessario creare un account delle risorse per ogni dispositivo della chat room di Teams in modo che possa accedere a Teams. Con questo account non è possibile usare l'autenticazione a due o più fattori. Richiedendo un secondo fattore, l'account non sarà in grado di accedere automaticamente all'app Sale di Teams dopo un riavvio. Tuttavia, è possibile abilitare l'autenticazione moderna per una sicurezza aggiuntiva per questo account. Possono inoltre essere distribuiti criteri di accesso condizionale basati sulla posizione per l'account delle risorse per impedire l'accesso all'account da una posizione non approvata. Per altre informazioni, vedere Uso [della condizione della posizione nei criteri di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)

Se possibile, è consigliabile creare l'account delle risorse in Azure AD. Anche se un account sincronizzato può lavorare con le sale di Teams in distribuzioni ibride, questi account sincronizzati spesso hanno difficoltà ad accedere alle sale di Teams e possono essere difficili da risolvere. Se si sceglie di usare un servizio federativo di terze parti per autenticare le credenziali per l'account della risorsa, assicurarsi che il provider di identità di terze parti risponda con l'attributo `wsTrustResponse` impostato su `urn:oasis:names:tc:SAML:1.0:assertion` .

## <a name="network-security"></a>Sicurezza di rete

In generale, Teams Room ha gli stessi requisiti di rete di qualsiasi client di Microsoft Teams. L'accesso tramite firewall e altri dispositivi di sicurezza è uguale per le sale di Teams di qualsiasi altro client di Microsoft Teams. Specifiche per le sale di Teams, le categorie elencate come "obbligatorie" per Teams devono essere aperte nel firewall. Le sale di Teams devono anche accedere a Windows Update, Microsoft Store e Microsoft Intune (se si usa Microsoft Intune per gestire i dispositivi). Per l'elenco completo di IP e URL necessari per microsoft Teams Room, vedere:

- **URL e intervalli** di indirizzi IP per Microsoft Teams [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Configurazione di Windows Update** [Server Update](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Prerequisiti di Microsoft Store** [per Microsoft Store per le aziende e la formazione](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Punti di accesso alla** rete di Microsoft [Intune per Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)

Se si usa il componente servizi gestiti Sale di Microsoft Teams di Microsoft Teams Rooms Premium, è anche necessario assicurarsi che le sale di Teams possano accedere agli URL seguenti:

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Sale di Teams è configurato per mantenersi automaticamente aggiornato con gli aggiornamenti di Windows più recenti, inclusi gli aggiornamenti della sicurezza. Teams Rooms installa gli eventuali aggiornamenti in sospeso ogni giorno a partire dalle 2:00 usando un criterio locale predefinito. Non è necessario usare altri strumenti per distribuire e applicare gli aggiornamenti di Windows. L'uso di altri strumenti per distribuire e applicare gli aggiornamenti può posticipare l'installazione delle patch di Windows e quindi portare a una distribuzione meno sicura. L'app Sale di Teams viene distribuita tramite Microsoft Store. Se i tuoi dispositivi sono concessi in licenza con Microsoft Teams Room Standard, tutte le nuove versioni dell'app vengono installate automaticamente durante il processo di distribuzione delle patch sereno. Se i dispositivi sono concessi in licenza con Microsoft Teams Room Premium e registrati nel servizio gestito da Microsoft, le nuove versioni dell'app Sale di Teams vengono installate in base al piano di implementazione definito.

I dispositivi Teams Room funzionano con la maggior parte dei protocolli di sicurezza 802.1X o basati sulla rete. Tuttavia, non è possibile testare le sale di Teams rispetto a tutte le possibili configurazioni di sicurezza di rete. Pertanto, se si verificano problemi di prestazioni che possono essere tracciati a problemi di prestazioni di rete, potrebbe essere necessario disabilitare questi protocolli se sono configurati nell'organizzazione.

Per ottenere prestazioni ottimali dei supporti multimediali in tempo reale, è consigliabile configurare il traffico multimediale di Teams in modo da bypassare i server proxy e altri dispositivi di sicurezza di rete. I supporti multimediali in tempo reale sono molto sensibili alla latenza e i server proxy e i dispositivi di sicurezza della rete possono ridurre significativamente la qualità audio e video degli utenti. Inoltre, poiché i supporti multimediali di Teams sono già crittografati, non esiste alcun vantaggio insod temporato dal passaggio del traffico attraverso un server proxy. Per altre informazioni, vedere Networking [(nel cloud),](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) il punto di vista di un architetto che discute dei consigli di rete per migliorare le prestazioni dei contenuti multimediali con Microsoft Teams e Microsoft Teams Room.

> [!IMPORTANT]
> Teams Room non supporta i server proxy autenticati.

I dispositivi di Teams Room non devono connettersi a una LAN interna. Considerare l'inserimento di sale teams in un segmento di rete sicuro con accesso diretto a Internet. Se la tua LAN interna viene compromessa, le opportunità del vettore di attacco verso Teams Room saranno ridotte.

È consigliabile connettere i dispositivi Di Teams Room a una rete cablata. L'uso di reti wireless su dispositivi Teams Rooms non è consigliato o certificato. Alcune funzionalità di connettività, ad esempio Wi-Fi, sono disabilitate per impostazione predefinita.

Proximity Join e altre funzionalità di Teams Room si basano Bluetooth. Tuttavia, l Bluetooth'implementazione della configurazione nei dispositivi Teams Room non consente la connessione di un dispositivo esterno a un dispositivo Teams Room. Bluetooth'uso della tecnologia su dispositivi Teams Rooms è attualmente limitato alla pubblicità di beacon e a connessioni proxy richieste. Il `ADV_NONCONN_INT` tipo di unità di dati del protocollo (PDU) viene usato nel beacon pubblicitario. Questo tipo di PDU è per i dispositivi non collegabili che pubblicizzano informazioni al dispositivo in ascolto. Non esiste alcuna associazione Bluetooth dispositivi nell'ambito di queste caratteristiche. Ulteriori informazioni sui Bluetooth sono disponibili sul sito [Bluetooth SIG.](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)
