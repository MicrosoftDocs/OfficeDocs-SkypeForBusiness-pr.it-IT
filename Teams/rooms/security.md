---
title: Sicurezza di Microsoft teams rooms
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
description: Informazioni su come proteggere i dispositivi di Microsoft teams rooms.
ms.openlocfilehash: d9968af4f386ed68d9a931d834082ba5362c5c33
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880882"
---
# <a name="microsoft-teams-rooms-security"></a>Sicurezza di Microsoft teams rooms

Microsoft collabora con i nostri partner per offrire una soluzione sicura e non richiede ulteriori azioni per proteggere le sale di Microsoft teams. In questo articolo vengono illustrate molte delle caratteristiche di sicurezza presenti nelle sale di teams.

> [!NOTE]
> Le sale di Microsoft teams non devono essere trattate come una normale workstation per utenti finali. Non solo i casi di utilizzo sono molto diversi, ma anche i profili di sicurezza predefiniti sono molto diversi.

I dati limitati degli utenti finali vengono archiviati nelle sale di teams. I dati degli utenti finali possono essere archiviati nei file di log solo per la risoluzione dei problemi e il supporto. In nessun punto può un partecipante a una riunione che usa le sale di teams copiare i file nel disco rigido o accedere come se stessi. Nessun dato utente finale viene trasferito o accessibile dal dispositivo Microsoft teams rooms.

Anche se gli utenti finali non possono inserire file in un disco rigido di teams rooms, Microsoft Defender è ancora abilitato. Le prestazioni di teams Rooms vengono testate con Microsoft Defender. La disattivazione di questo o l'aggiunta di software di sicurezza endpoint può determinare risultati imprevedibili e potenziali degradazioni del sistema.

## <a name="hardware-security"></a>Sicurezza hardware

In un ambiente di teams Rooms esiste un modulo di calcolo centrale che esegue Windows 10. Ogni modulo di calcolo certificato deve avere una soluzione di montaggio sicura, uno slot di blocco di sicurezza (ad esempio, blocco Kensington) e misure di sicurezza per l'accesso alle porte di I/O per impedire la connessione di dispositivi non autorizzati. È anche possibile disabilitare porte specifiche tramite la configurazione UEFI (Unified Extensible Firmware Interface).

Ogni modulo di calcolo certificato deve essere disponibile con la tecnologia conforme al TPM (Trusted Platform Module) 2,0 abilitata per impostazione predefinita. TPM viene usato per crittografare le informazioni di accesso per l'account delle risorse di teams rooms.

L'avvio sicuro è abilitato per impostazione predefinita. Secure Boot è uno standard di sicurezza sviluppato dai membri dell'industria del PC per assicurarsi che un dispositivo si avvii usando solo software considerato attendibile dall'OEM (Original Equipment Manufacturer). Quando il PC viene avviato, il firmware controlla la firma di ogni parte del software di avvio, inclusi i driver UEFI (nota anche come Option ROMs), le applicazioni EFI e il sistema operativo. Se le firme sono valide, il PC si avvia e il firmware dà il controllo al sistema operativo. Per altre informazioni, Vedi [Secure Boot](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

L'accesso alle impostazioni UEFI è possibile solo allegando una tastiera e un mouse fisici. In questo modo non è possibile accedere a UEFI tramite la console abilitata per il tocco sale teams, nonché qualsiasi altro display abilitato per il tocco collegato alle sale di teams.

La protezione DMA (Direct Memory Access) del kernel è un'impostazione di Windows 10 abilitata nelle sale di teams. Grazie a questa caratteristica, il sistema operativo e il firmware di sistema proteggono i sistemi con attacchi DMA malevoli e non intenzionali per tutti i dispositivi con funzionalità DMA:

- Durante il processo di avvio.

- Contro il DMA malevolo da dispositivi connessi a porte interne/esterne con capacità di DMA, come M. 2 slot PCIe e Thunderbolt 3, durante il runtime del sistema operativo.

Teams Rooms consente inoltre l'integrità del codice protetto da hypervisor (HVCI). Una delle funzionalità fornite da HVCI è Credential Guard. La protezione delle credenziali offre i vantaggi seguenti:

- **Sicurezza hardware** NTLM, Kerberos e gestione credenziali sfruttano le funzionalità di sicurezza della piattaforma, tra cui l'avvio sicuro e la virtualizzazione, per proteggere le credenziali.

- **Sicurezza basata sulla virtualizzazione** Le credenziali derivate da Windows NTLM e Kerberos e altri segreti vengono eseguiti in un ambiente protetto isolato dal sistema operativo in esecuzione.

- **Migliore protezione contro le minacce persistenti avanzate** Quando le credenziali del dominio di Credential Manager, NTLM e Kerberos sono protette con la sicurezza basata sulla virtualizzazione, le tecniche e gli strumenti di attacco per il furto delle credenziali usate in molti attacchi mirati sono bloccati. Il malware in uso nel sistema operativo con privilegi amministrativi non può estrarre segreti protetti dalla sicurezza basata sulla virtualizzazione.

## <a name="software-security"></a>Sicurezza del software

Dopo Microsoft Windows Boots, sale teams accede automaticamente a un account utente di Windows locale denominato Skype. L'account Skype non ha una password. Per rendere sicura la sessione dell'account Skype, vengono eseguite le operazioni seguenti.

> [!IMPORTANT]
> Non cambiare la password o modificare l'account utente locale Skype. In questo modo puoi impedire che le sale di Team accedano automaticamente.

L'app Microsoft teams Rooms viene eseguita usando la funzionalità di accesso assegnata disponibile in Windows 10 1903 e versioni successive. L'accesso assegnato è una funzionalità di Windows 10 che limita i punti di ingresso dell'applicazione esposti all'utente. Questo è ciò che consente la modalità Kiosk Single-app. Usando l'icona di avvio delle shell, sale teams è configurato come dispositivo Kiosk che esegue un'applicazione desktop Windows come interfaccia utente. L'app Microsoft teams Rooms sostituisce la shell predefinita (explorer.exe) che in genere viene eseguita quando un utente esegue l'accesso. In altre parole, la shell di Esplora risorse tradizionale non viene avviata affatto. Questo riduce notevolmente la superficie di vulnerabilità delle sale di Microsoft teams all'interno di Windows. Per altre informazioni, vedere [configurare i chioschi e i segni digitali nelle edizioni desktop di Windows](https://docs.microsoft.com/windows/configuration/kiosk-methods).

Se si decide di eseguire un'analisi di sicurezza o un punto di riferimento del centro per la sicurezza Internet (CIS) nelle sale di teams, l'analisi può essere eseguita solo nel contesto di un account di amministratore locale quando l'account utente Skype non supporta l'esecuzione di applicazioni diverse dall'app teams rooms. Molte delle caratteristiche di sicurezza applicate al contesto utente Skype non si applicano ad altri utenti locali e, di conseguenza, queste analisi di sicurezza non esportano il blocco di sicurezza completo applicato all'account Skype. Di conseguenza, non è consigliabile eseguire un'analisi locale nelle sale di teams. È tuttavia possibile eseguire test di penetrazione esterni se lo si desidera. Per questo motivo, ti consigliamo di eseguire test di penetrazione esterni nei dispositivi di teams Rooms anziché eseguire scansioni locali.

Inoltre, i criteri di blocco vengono applicati per limitare l'uso delle caratteristiche non amministrative. Un filtro da tastiera è abilitato per intercettare e bloccare le combinazioni di tasti potenzialmente non sicure che non sono coperte da criteri di accesso assegnati. Solo gli utenti con diritti amministrativi locali o di dominio possono accedere a Windows per gestire le sale di teams. Questi e altri criteri applicati a Windows nei dispositivi Microsoft teams Rooms vengono valutati e testati continuamente durante il ciclo di vita del prodotto.

## <a name="account-security"></a>Sicurezza dell'account

I dispositivi teams Rooms includono un account di amministrazione denominato "amministratore" con una password predefinita. Ti consigliamo vivamente di modificare la password predefinita al più presto dopo aver completato la configurazione.

L'account di amministratore non è necessario per il corretto funzionamento dei dispositivi di teams Rooms e può essere rinominato o anche eliminato. Tuttavia, prima di eliminare l'account amministratore, assicurati di configurare un account di amministratore locale alternativo configurato prima di rimuovere quello fornito con i dispositivi di teams rooms. Per altre informazioni su come modificare una password per un account di Windows locale usando gli strumenti predefiniti di Windows o PowerShell, vedere quanto segue:

- [Cambiare o reimpostare la password di Windows](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

È anche possibile importare account di dominio nel gruppo amministratore locale di Windows. Puoi eseguire questa operazione per gli account di Azure AD tramite Intune. Per altre informazioni, vedere [criteri CSP-RestrictedGroups.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups).

> [!CAUTION]
> Se si elimina o si disabilita l'account amministratore prima di concedere le autorizzazioni di amministratore locale a un altro account locale o di dominio, è possibile che si perda la possibilità di gestire il dispositivo teams rooms. In questo caso, è necessario reimpostare il dispositivo sulle impostazioni originali e completare di nuovo il processo di configurazione.
>
> Non concedere le autorizzazioni di amministratore locale all'account utente Skype.

Windows Configuration designer può essere usato per creare pacchetti di provisioning di Windows 10. Oltre a modificare la password di amministratore locale, è anche possibile eseguire operazioni come la modifica del nome del computer e la registrazione in Azure Active Directory. Per altre informazioni sulla creazione di un pacchetto di provisioning di Windows Configuration designer, vedere [provisioning di pacchetti per Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).

È necessario creare un account delle risorse per ogni dispositivo di teams rooms in modo che possa accedere ai team. Non è possibile usare l'autenticazione a due fattori o a più fattori con questo account. Richiedere un secondo fattore impedirebbe all'account di accedere automaticamente all'app teams rooms dopo un riavvio. Tuttavia, puoi abilitare l'autenticazione moderna per la sicurezza aggiuntiva per questo account. Inoltre, i criteri di accesso condizionale basati sulla posizione possono essere distribuiti per l'account delle risorse per impedire l'accesso all'account da una posizione non approvata. Per altre informazioni, vedere [uso della condizione di posizione in un criterio di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)

È consigliabile creare l'account delle risorse in Azure AD, se possibile. Mentre un account sincronizzato può lavorare con le sale di teams in distribuzioni ibride, questi account sincronizzati spesso hanno difficoltà ad accedere alle sale di teams e possono essere difficili da risolvere. Se si sceglie di usare un servizio federativo di terze parti per autenticare le credenziali per l'account delle risorse, verificare che l'IDP di terze parti risponda con l' `wsTrustResponse` attributo impostato su `urn:oasis:names:tc:SAML:1.0:assertion` .

## <a name="network-security"></a>Sicurezza di rete

In generale, le sale di teams hanno gli stessi requisiti di rete di qualsiasi client Microsoft teams. L'accesso tramite firewall e altri dispositivi di sicurezza è lo stesso per le sale di teams come per qualsiasi altro client Microsoft teams. Specifiche per le sale di teams, le categorie elencate come "necessarie" per i team devono essere aperte nel firewall. In teams Rooms è inoltre necessario l'accesso a Windows Update, Microsoft Store e Microsoft Intune (se si usa Microsoft Intune per gestire i dispositivi). Per l'elenco completo degli indirizzi IP e degli URL necessari per Microsoft teams rooms, vedere:

- [URL e intervalli di indirizzi IP di](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams) **Microsoft teams** Office 365
- **Windows Update** [configura WSUS](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- Prerequisiti di **Microsoft Store** [per Microsoft Store per le aziende e l'istruzione](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
-  [Punti di rete di Microsoft Intune per Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)

Se si usa il componente Microsoft teams Rooms Managed Services di Microsoft teams Rooms Premium, è anche necessario assicurarsi che le sale di teams possano accedere agli URL seguenti:

- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- gj3ft-hub.azure-devices.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- prod-48.westus.logic.azure.com
- prod-08.westus.logic.azure.com
- prod-62.westus.logic.azure.com
- prod-65.westus.logic.azure.com
- prod-05.westus.logic.azure.com

Sale teams è configurato per mantenersi automaticamente aggiornato con gli aggiornamenti più recenti di Windows, inclusi gli aggiornamenti della sicurezza. Sale teams installa tutti gli aggiornamenti in sospeso ogni giorno a partire dalle 2:00 usando un criterio locale preimpostato. Non è necessario usare altri strumenti per distribuire e applicare gli aggiornamenti di Windows. L'uso di strumenti aggiuntivi per distribuire e applicare gli aggiornamenti può ritardare l'installazione di patch di Windows e quindi portare a una distribuzione meno sicura. L'app teams Rooms viene distribuita con Microsoft Store. Se i tuoi dispositivi sono concessi in licenza con Microsoft teams rooms standard, tutte le nuove versioni dell'app vengono installate automaticamente durante il processo di patch notturno. Se i dispositivi sono concessi in licenza con Microsoft teams Rooms Premium e registrati nel servizio Microsoft Managed Service, sono installate nuove versioni dell'app teams Rooms per il piano di implementazione definito.

I dispositivi teams Rooms funzionano con la maggior parte dei protocolli di sicurezza 802.1 X o di altri network. Tuttavia, non siamo in grado di testare le sale di teams contro tutte le possibili configurazioni di sicurezza della rete. Di conseguenza, se si verificano problemi di prestazioni che possono essere rintracciati in problemi di prestazioni di rete, potrebbe essere necessario disabilitare questi protocolli se sono configurati nell'organizzazione.

Per ottenere prestazioni ottimali in tempo reale, è consigliabile configurare il traffico multimediale di teams per aggirare i server proxy e altri dispositivi di sicurezza della rete. L'elemento multimediale in tempo reale è molto sensibile alla latenza e i server proxy e i dispositivi di sicurezza di rete possono degradare significativamente la qualità audio e video degli utenti. Inoltre, dato che il supporto di teams è già crittografato, non c'è alcun vantaggio tangibile che passa il traffico attraverso un server proxy. Per altre informazioni, Vedi [Networking up (per il cloud): un punto di vista di un architetto](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) che discute le raccomandazioni di rete per migliorare le prestazioni dei contenuti multimediali con Microsoft teams e Microsoft teams rooms.

> [!IMPORTANT]
> Sale teams non supporta i server proxy autenticati.

I dispositivi teams Rooms non devono connettersi a una LAN interna. Valutare la possibilità di collocare le sale di teams in un segmento di rete sicuro con accesso Internet diretto. Se la LAN interna viene compromessa, le opportunità di attacco vettoriali per le sale di team saranno ridotte.

Ti consigliamo vivamente di connettere i dispositivi delle sale team a una rete cablata. L'uso delle reti wireless nei dispositivi di teams Rooms non è raccomandato o certificato. Alcune caratteristiche di connettività, ad esempio Wi-Fi senso, sono disabilitate per impostazione predefinita.

Join di prossimità e altre funzionalità delle sale teams si basano su Bluetooth. Tuttavia, l'implementazione Bluetooth nei dispositivi teams Rooms non consente la connessione di un dispositivo esterno a un dispositivo di teams rooms. L'uso della tecnologia Bluetooth nei dispositivi di teams Rooms è attualmente limitato ai beacon pubblicitari e alle connessioni prossimali richieste. Il `ADV_NONCONN_INT` tipo di unità dati Protocol (PDU) viene usato nel Beacon pubblicitario. Questo tipo di PDU è per i dispositivi non collegabili che pubblicizzano informazioni sul dispositivo di ascolto. Non è possibile associare un dispositivo Bluetooth come parte di queste funzionalità. Ulteriori informazioni sui protocolli Bluetooth si trovano nel [sito web Bluetooth SIG](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/).
