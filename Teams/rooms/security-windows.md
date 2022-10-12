---
title: sicurezza di Microsoft Teams Rooms per Windows
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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Scopri come proteggere il tuo Microsoft Teams Rooms per i dispositivi Windows.
ms.openlocfilehash: b35d856afb7ca044388802aa514039bd9b8d40d3
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532425"
---
# <a name="microsoft-teams-rooms-for-windows-security"></a>sicurezza di Microsoft Teams Rooms per Windows

Microsoft collabora con i propri partner per offrire una soluzione sicura e non richiede ulteriori azioni per proteggere Microsoft Teams Rooms per Windows. Questo articolo descrive molte delle funzionalità di sicurezza disponibili in Teams Rooms per Windows.

Per informazioni sulla sicurezza in Teams Rooms per dispositivi Android, vedere [Microsoft Teams Rooms per la sicurezza di Android](security-android.md).

> [!NOTE]
> Microsoft Teams Rooms non devono essere trattate come una tipica workstation per l'utente finale. Non solo i casi d'uso sono molto diversi, ma anche i profili di sicurezza predefiniti sono molto diversi.
> Questo articolo si applica ai dispositivi Microsoft Teams Rooms in esecuzione in Windows.

I dati limitati degli utenti finali vengono archiviati in Teams Rooms. I dati degli utenti finali possono essere archiviati nei file di log solo per la risoluzione dei problemi e il supporto. In nessun momento un partecipante a una riunione può usare Teams Rooms copiare file nel disco rigido o accedere come se stesso. Nessun dato dell'utente finale viene trasferito o accessibile dal dispositivo Microsoft Teams Rooms.

Anche se gli utenti finali non possono inserire file in un disco rigido Teams Rooms, Microsoft Defender è ancora abilitato. Teams Rooms prestazioni vengono testate con Microsoft Defender. La disabilitazione o l'aggiunta di software per la sicurezza degli endpoint può causare risultati imprevedibili e una potenziale riduzione delle prestazioni del sistema.

## <a name="hardware-security"></a>Sicurezza hardware

In un ambiente di Teams Rooms esiste un modulo di calcolo centrale che esegue Windows 10 IoT Enterprise edizione. Ogni modulo di calcolo certificato deve avere una soluzione di montaggio sicura, uno slot per il blocco di sicurezza (ad esempio Kensington Lock) e misure di sicurezza per l'accesso alla porta I/O per impedire la connessione di dispositivi non autorizzati. È anche possibile disabilitare porte specifiche tramite la configurazione UEFI (Unified Extensible Firmware Interface).

Ogni modulo di calcolo certificato deve essere fornito con una tecnologia conforme a Trusted Platform Module (TPM) 2.0 abilitata per impostazione predefinita. TPM viene usato per crittografare le informazioni di accesso per l'account della risorsa Teams Rooms.

L'avvio protetto è abilitato per impostazione predefinita. Avvio protetto è uno standard di sicurezza sviluppato dai membri del settore dei PC per garantire che un dispositivo venga avviato usando solo software considerato attendibile dall'OEM (Original Equipment Manufacturer). All'avvio del PC, il firmware controlla la firma di ogni componente del software di avvio, inclusi i driver del firmware UEFI (noti anche come ROM di opzione), le applicazioni EFI e il sistema operativo. Se le firme sono valide, il PC viene avviato e il firmware consente di controllare il sistema operativo. Per altre informazioni, vedi [Avvio protetto](/windows-hardware/design/device-experiences/oem-secure-boot).

L'accesso alle impostazioni UEFI è possibile solo collegando una tastiera fisica e un mouse. In questo modo si impedisce di accedere alla UEFI tramite la console abilitata per il tocco Teams Rooms e qualsiasi altro schermo abilitato per il tocco collegato a Teams Rooms.

Protezione DMA (Kernel Direct Memory Access) è un'impostazione Windows 10 abilitata in Teams Rooms. Con questa funzionalità, il sistema operativo e il firmware di sistema proteggono il sistema da attacchi DMA dannosi e indesiderati per tutti i dispositivi che supporta DMA:With this feature, the OS and the system firmware protect the system against malicious and inintended DMA attacks for all DMA-capable devices:

- Durante il processo di avvio.

- Contro DMA dannosi da dispositivi connessi a porte interne/esterne facilmente accessibili, come gli slot M.2 PCIe e Thunderbolt 3, durante il runtime del sistema operativo.

Teams Rooms inoltre abilita l'integrità del codice (HVCI) protetta da Hypervisor. Una delle funzionalità fornite da HVCI è Credential Guard. Credential Guard offre i seguenti vantaggi:

- **Sicurezza hardware** NTLM, Kerberos e Gestione credenziali sfruttano le funzionalità di sicurezza della piattaforma, tra cui avvio protetto e virtualizzazione, per proteggere le credenziali.

- **Sicurezza basata sulla virtualizzazione** Le credenziali derivate di Windows NTLM e Kerberos e altri segreti vengono eseguiti in un ambiente protetto isolato dal sistema operativo in esecuzione.

- **Migliore protezione dalle minacce persistenti avanzate** Quando le credenziali di dominio di Gestione credenziali, NTLM e Kerberos sono protette tramite la sicurezza basata sulla virtualizzazione, vengono bloccati gli strumenti e le tecniche di attacco per il furto di credenziali usate in molti attacchi mirati. Il malware in esecuzione nel sistema operativo con privilegi amministrativi non può estrarre segreti protetti dalla sicurezza basata sulla virtualizzazione.

## <a name="software-security"></a>Sicurezza software

Dopo l'avvio di Microsoft Windows, Teams Rooms accede automaticamente a un account utente windows locale denominato Skype. L'account Skype non ha una password. Per rendere sicura la sessione dell'account Skype, vengono eseguiti i passaggi seguenti.

> [!IMPORTANT]
> Non cambiare la password o modificare l'account utente Skype locale. In questo modo è possibile impedire Teams Rooms di eseguire automaticamente l'accesso.

L'app Microsoft Teams Rooms viene eseguita con la caratteristica Accesso assegnato disponibile nel Windows 10 1903 e versioni successive. Access assegnato è una caratteristica di Windows 10 che limita i punti di ingresso dell'applicazione esposti all'utente. Questo è ciò che consente la modalità chiosco singola app. Con Shell Launcher, Teams Rooms è configurato come dispositivo chiosco multimediale che esegue un'applicazione desktop Windows come interfaccia utente. L'app Microsoft Teams Rooms sostituisce la shell predefinita (explorer.exe) che in genere viene eseguita quando un utente accede. In altre parole, la shell di Explorer tradizionale non viene avviata affatto. In questo modo si riduce notevolmente la vulnerabilità Microsoft Teams Rooms surface all'interno di Windows. Per altre informazioni, vedi [Configurare chioschi multimediali e segnali digitali nelle edizioni desktop di Windows](/windows/configuration/kiosk-methods).

Se decidi di eseguire un'analisi della sicurezza o un benchmark del Centro per la sicurezza Internet (CIS) su Teams Rooms, l'analisi può essere eseguita solo nel contesto di un account amministratore locale perché l'account utente Skype non supporta l'esecuzione di applicazioni diverse dall'app Teams Rooms. Molte delle funzionalità di sicurezza applicate al contesto dell'utente Skype non si applicano ad altri utenti locali e, di conseguenza, queste analisi di sicurezza non visualizzeranno il blocco di sicurezza completo applicato all'account Skype. Pertanto, non è consigliabile eseguire un'analisi locale su Teams Rooms. Tuttavia, è possibile eseguire test di penetrazione esterna, se lo si desidera. Per questo motivo, è consigliabile eseguire test di penetrazione esterni su dispositivi Teams Rooms invece di eseguire scansioni locali.

Inoltre, i criteri di blocco vengono applicati per limitare l'uso di caratteristiche non amministrative. Un filtro della tastiera è abilitato per intercettare e bloccare le combinazioni di tastiera potenzialmente non sicure che non sono coperte dai criteri di accesso assegnato. Solo gli utenti con diritti amministrativi locali o di dominio possono accedere a Windows per gestire Teams Rooms. Questi e altri criteri applicati a Windows nei dispositivi Microsoft Teams Rooms vengono continuamente valutati e testati durante il ciclo di vita del prodotto.

## <a name="account-security"></a>Sicurezza dell'account

Teams Rooms dispositivi includono un account amministrativo denominato "Amministrazione" con una password predefinita. È consigliabile cambiare la password predefinita non appena possibile al termine della configurazione.

L'account Amministrazione non è necessario per il corretto funzionamento di Teams Rooms dispositivi e può essere rinominato o anche eliminato. Tuttavia, prima di eliminare l'account Amministrazione, assicurati di configurare un account amministratore locale alternativo configurato prima di rimuovere quello fornito con Teams Rooms dispositivi. Per altre informazioni su come cambiare una password per un account Windows locale usando gli strumenti predefiniti di Windows o PowerShell, vedi:

- [Cambiare o reimpostare la password di Windows](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser#example-2--change-the-password-on-an-account)

È anche possibile importare account di dominio nel gruppo amministratore di Windows locale. È possibile eseguire questa operazione per gli account di Azure AD usando Intune. Per altre informazioni, vedere [Criteri CSP - RestrictedGroups.](/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!NOTE]
> Se utilizzi console Crestron, assicurati di aggiornare anche la password di Amministrazione nella console e nel modulo di calcolo. Per altre informazioni, contatta Crestron.

> [!CAUTION]
> Se si elimina o disabilita l'account Amministrazione prima di concedere autorizzazioni di amministratore locale a un altro account locale o di dominio, si potrebbe perdere la possibilità di amministrare il dispositivo Teams Rooms. In questo caso, dovrai ripristinare le impostazioni originali del dispositivo e completare nuovamente il processo di configurazione.

Non concedere autorizzazioni di amministratore locale all'account utente Skype.

Progettazione configurazione di Windows può essere usato per creare pacchetti di provisioning Windows 10. Oltre a modificare la password Amministrazione locale, è anche possibile eseguire operazioni come la modifica del nome del computer e la registrazione in Azure Active Directory. Per altre informazioni sulla creazione di un pacchetto di provisioning di Progettazione configurazione di Windows, vedi [Pacchetti di provisioning per Windows 10](/windows/configuration/provisioning-packages/provisioning-packages).

È necessario creare un account di risorsa per ogni dispositivo Teams Rooms in modo che possa accedere a Teams. Con questo account non è possibile usare l'autenticazione a due fattori o a più fattori. Richiedere un secondo fattore impedirebbe all'account di accedere automaticamente all'app Teams Rooms dopo un riavvio. Tuttavia, è possibile abilitare l'autenticazione moderna per una maggiore sicurezza per questo account. È anche possibile distribuire criteri di accesso condizionale di Azure Active Directory e criteri di conformità Intune per proteggere l'account delle risorse. Per altre informazioni, vedere [Accesso condizionale supportato e criteri di conformità dei dispositivi Intune per Microsoft Teams Rooms](supported-ca-and-compliance-policies.md) e [accesso condizionale e conformità Intune per Microsoft Teams Rooms](conditional-access-and-compliance-for-devices.md)

Se possibile, è consigliabile creare l'account delle risorse in Azure AD. Anche se un account sincronizzato può funzionare con Teams Rooms nelle distribuzioni ibride, questi account sincronizzati spesso hanno difficoltà ad accedere a Teams Rooms e possono essere difficili da risolvere. Se si sceglie di usare un servizio federativo di terze parti per autenticare le credenziali per l'account della risorsa, assicurarsi che l'IDP di terze parti risponda con l'attributo `wsTrustResponse` impostato su `urn:oasis:names:tc:SAML:1.0:assertion`.

## <a name="network-security"></a>Sicurezza di rete

In generale, Teams Rooms ha gli stessi requisiti di rete di qualsiasi client di Microsoft Teams. L'accesso tramite firewall e altri dispositivi di sicurezza è lo stesso per Teams Rooms di qualsiasi altro client di Microsoft Teams. Specifiche per Teams Rooms, le categorie elencate come "obbligatorie" per Teams devono essere aperte nel firewall. Teams Rooms deve anche accedere a Windows Update, Microsoft Store e Microsoft Intune (se usi Microsoft Intune per gestire i tuoi dispositivi). Per l'elenco completo di INDIRIZZI IP e URL necessari per Microsoft Teams Rooms, vedere:

- **Microsoft Teams** [Office 365 URL e intervalli di indirizzi IP](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)
- **Windows Update** [Configurare WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- Prerequisiti di **Microsoft Store** [per Microsoft Store per le aziende e formazione](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **endpoint di** [rete Microsoft Intune per Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Se si usa il componente Microsoft Teams Rooms servizi gestiti di Microsoft Teams Rooms Pro, è anche necessario assicurarsi che Teams Rooms possano accedere agli URL seguenti:

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Teams Rooms è configurato per mantenere automaticamente le patch con gli ultimi aggiornamenti di Windows, inclusi gli aggiornamenti della sicurezza. Teams Rooms installa tutti i giorni gli aggiornamenti in sospeso a partire alle 2:00 usando criteri locali predefiniti. Non è necessario usare altri strumenti per distribuire e applicare Windows Aggiornamenti. L'uso di strumenti aggiuntivi per distribuire e applicare gli aggiornamenti può ritardare l'installazione delle patch di Windows e quindi condurre a una distribuzione meno sicura. L'app Teams Rooms viene distribuita tramite Microsoft Store.

<!-- LICENSE-REVIEW If your devices are licensed with Microsoft Teams Rooms Standard, any new versions of the app are automatically installed during the nightly patching process. If your devices are licensed with Microsoft Teams Rooms Premium and enrolled in the Microsoft Managed Service, new versions of the Teams Rooms app are installed per your defined rollout plan. -->

Teams Rooms i dispositivi funzionano con la maggior parte dei protocolli di sicurezza 802.1X o basati su rete. Tuttavia, non è possibile testare Teams Rooms con tutte le possibili configurazioni di sicurezza di rete. Pertanto, se si verificano problemi di prestazioni che possono essere rilevati da problemi di prestazioni di rete, potrebbe essere necessario disabilitare questi protocolli se sono configurati nell'organizzazione.

Per ottenere prestazioni ottimali dai supporti in tempo reale, è consigliabile configurare il traffico multimediale di Teams in modo da ignorare i server proxy e altri dispositivi di sicurezza di rete. I supporti in tempo reale sono sensibili alla latenza e i server proxy e i dispositivi di sicurezza di rete possono ridurre significativamente la qualità audio e video degli utenti. Inoltre, poiché i contenuti multimediali di Teams sono già crittografati, non c'è alcun vantaggio tangibile nel passaggio del traffico attraverso un server proxy. Per altre informazioni, vedere [Networking up (to the cloud) — Punto di vista di un architetto](/microsoft-365/solutions/networking-design-principles) che discute i consigli di rete per migliorare le prestazioni dei supporti con Microsoft Teams e Microsoft Teams Rooms.

> [!IMPORTANT]
> Teams Rooms non supporta i server proxy autenticati.

Teams Rooms dispositivi non devono connettersi a una LAN interna. Considerare l'inserimento di Teams Rooms in un segmento di rete sicuro con accesso diretto a Internet. Se la LAN interna viene compromessa, le opportunità del vettore di attacco verso Teams Rooms verranno ridotte.

Ti consigliamo vivamente di connettere i dispositivi Teams Rooms a una rete cablata. L'uso di reti wireless su dispositivi Teams Rooms non è consigliato o certificato. Alcune funzionalità di connettività, ad esempio Sensore Wi-Fi, sono disabilitate per impostazione predefinita.

L'aggiunta per prossimità e altre funzionalità di Teams Rooms si basano sul Bluetooth. Tuttavia, l'implementazione Bluetooth nei dispositivi Teams Rooms non consente la connessione di un dispositivo esterno a un dispositivo Teams Rooms. L'uso della tecnologia Bluetooth nei dispositivi Teams Rooms è attualmente limitato agli annunci beacon e alle connessioni proximal. Il `ADV_NONCONN_INT` tipo di unità di dati del protocollo (PDU) viene utilizzato nel advertising beacon. Questo tipo di PDU è per le informazioni pubblicitarie sui dispositivi non collegabili al dispositivo di ascolto. Non esiste alcuna associazione di dispositivi Bluetooth nell'ambito di queste funzionalità. Ulteriori dettagli sui protocolli Bluetooth sono disponibili sul [sito Web Bluetooth SIG](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/).
