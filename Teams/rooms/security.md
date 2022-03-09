---
title: Microsoft Teams Rooms sicurezza
ms.author: czawideh
author: cazawideh
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
description: Scopri come proteggere i tuoi dispositivi Microsoft Teams Rooms mobili.
ms.openlocfilehash: bbb61023772e5116d2ca96171d30649ab85bf68c
ms.sourcegitcommit: 109be23768ae183e07a0833fa9a9e5cb0369cb43
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2022
ms.locfileid: "63368381"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams Rooms sicurezza

Microsoft collabora con i nostri partner per offrire una soluzione sicura e che non richiede azioni aggiuntive per proteggere Microsoft Teams Rooms. Questo articolo illustra molte delle funzionalità di sicurezza disponibili in Teams Rooms.

> [!NOTE]
> Microsoft Teams Rooms non deve essere considerato come una tipica workstation per l'utente finale. Non solo i casi d'uso sono notevolmente diversi, ma anche i profili di sicurezza predefiniti sono molto diversi.
> Questo articolo si applica ai Microsoft Teams Rooms in esecuzione in Windows.

I dati limitati per gli utenti finali vengono archiviati Teams Rooms. I dati degli utenti finali possono essere archiviati nei file di log solo per la risoluzione dei problemi e il supporto. In nessun momento un partecipante a una riunione può Teams Rooms copiare i file nel disco rigido o accedere come se stessi. Nessun dato dell'utente finale viene trasferito o accessibile dal Microsoft Teams Rooms dispositivo.

Anche se gli utenti finali non possono inserire file in un Teams Rooms disco rigido, Microsoft Defender è ancora abilitato. Teams Rooms prestazioni vengono testate con Microsoft Defender. La disabilitazione di questo software o l'aggiunta di software per la sicurezza degli endpoint può portare a risultati imprevedibili e a potenziali degradazioni del sistema.

## <a name="hardware-security"></a>Sicurezza hardware

In un Teams Rooms, è presente un modulo di calcolo centrale che viene eseguito Windows 10 IoT Enterprise edizione. Ogni modulo di calcolo certificato deve avere una soluzione di montaggio sicura, uno slot di blocco della sicurezza (ad esempio, il blocco di Kensington) e misure di sicurezza per l'accesso alla porta I/O per impedire la connessione di dispositivi non autorizzati. È anche possibile disabilitare porte specifiche tramite la configurazione UEFI (Unified Extensible Firmware Interface).

Ogni modulo di elaborazione certificato deve essere spedito con la tecnologia compatibile TPM (Trusted Platform Module) 2.0 abilitata per impostazione predefinita. Il TPM viene usato per crittografare le informazioni di accesso per l'account Teams Rooms risorsa.

L'avvio sicuro è abilitato per impostazione predefinita. L'avvio sicuro è uno standard di sicurezza sviluppato dai membri del settore dei PC per garantire che un dispositivo si scarifi con il solo software considerato attendibile dal produttore OEM (Original Equipment Manufacturer). All'avvio del PC, il firmware controlla la firma di ogni parte del software di avvio, inclusi i driver del firmware UEFI (noti anche come ROM delle opzioni), le applicazioni EFI e il sistema operativo. Se le firme sono valide, il PC si avvia e il firmware dà il controllo al sistema operativo. Per altre informazioni, vedere [Avvio sicuro](/windows-hardware/design/device-experiences/oem-secure-boot).

L'accesso alle impostazioni UEFI è possibile solo collegando una tastiera e un mouse fisici. In questo modo si impedisce l'accesso a UEFI tramite la console Teams Rooms abilitata per il tocco e qualsiasi altro display abilitato per il tocco collegato a Teams Rooms.

La protezione DMA (Kernel Direct Memory Access) è un'Windows 10 attivata in Teams Rooms. Con questa funzionalità, il sistema operativo e il firmware di sistema proteggono il sistema da attacchi DMA dannosi e indesiderati per tutti i dispositivi compatibili con DMA:

- Durante il processo di avvio.

- Contro DMA dannosi da parte di dispositivi connessi a porte DMA interne/esterne facilmente accessibili, come slot PCIe M.2 e Thunderbolt 3, durante il runtime del sistema operativo.

Teams Rooms abilita anche l'integrità del codice protetto da Hypervisor (HVCI). Una delle funzionalità fornite da HVCI è Credential Guard. Credential Guard offre i vantaggi seguenti:

- **Sicurezza hardware** NTLM, Kerberos e Gestione credenziali sfruttano le funzionalità di sicurezza della piattaforma, tra cui l'avvio sicuro e la virtualizzazione, per proteggere le credenziali.

- **La sicurezza basata sulla** virtualizzazione Windows credenziali derivate da NTLM e Kerberos e altri segreti vengono eseguiti in un ambiente protetto isolato dal sistema operativo in esecuzione.

- **Maggiore protezione dalle minacce persistenti avanzate** Quando le credenziali di dominio di Gestione credenziali, NTLM e le credenziali derivate da Kerberos sono protette con la sicurezza basata sulla virtualizzazione, le tecniche e gli strumenti di attacco del furto di credenziali usati in molti attacchi mirati vengono bloccati. Il malware in esecuzione nel sistema operativo con privilegi amministrativi non può estrarre segreti protetti dalla sicurezza basata sulla virtualizzazione.

## <a name="software-security"></a>Sicurezza del software

Dopo l'avvio Windows microsoft, Teams Rooms automaticamente un account utente Windows locale denominato Skype. L Skype account non ha una password. Per rendere sicura la Skype dell'account, eseguire le operazioni seguenti.

> [!IMPORTANT]
> Non modificare la password o l'account utente Skype locale. In questo modo è possibile Teams Rooms automaticamente l'accesso.

L Microsoft Teams Rooms app viene eseguita usando la caratteristica Accesso assegnato disponibile in Windows 10 1903 e versioni successive. Accesso assegnato è una caratteristica di Windows 10 che limita i punti di ingresso dell'applicazione esposti all'utente. Questo è ciò che abilita la modalità chiosco multimediale a singola app. L'icona di avvio della shell Teams Rooms è configurata come dispositivo chiosco multimediale che esegue un'Windows desktop come interfaccia utente. L Microsoft Teams Rooms app sostituisce la shell predefinita (explorer.exe) che in genere viene eseguita quando un utente esegue l'accesso. In altre parole, la shell tradizionale di Explorer non viene avviata affatto. In questo modo si riduce notevolmente Microsoft Teams Rooms della vulnerabilità all'interno Windows. Per altre informazioni, vedere [Configurare chioschi e segnali digitali nelle Windows desktop](/windows/configuration/kiosk-methods).

Se si decide di eseguire un'analisi della sicurezza o un benchmark cis (Center for Internet Security) su Teams Rooms, l'analisi può essere eseguita solo nel contesto di un account di amministratore locale perché l'account utente di Skype non supporta le applicazioni in esecuzione diverse dall'app Teams Rooms. Molte delle caratteristiche di sicurezza applicate al contesto utente di Skype non si applicano ad altri utenti locali e, di conseguenza, queste analisi della sicurezza non vengono applicate all'account Skype. Di conseguenza, non è consigliabile eseguire un'analisi locale in Teams Rooms. Tuttavia, se si desidera, è possibile eseguire test di penetrazione esterni. Per questo, è consigliabile eseguire test di penetrazione esterni su Teams Rooms invece di eseguire scansioni locali.

Inoltre, i criteri di blocco vengono applicati per limitare l'uso di funzionalità non amministrative. Un filtro della tastiera è abilitato per intercettare e bloccare combinazioni di tasti potenzialmente non sicure non coperte dai criteri di accesso assegnato. Solo gli utenti con diritti amministrativi locali o di dominio possono accedere Windows gestire Teams Rooms. Questi e altri criteri applicati ai Windows nei dispositivi Microsoft Teams Rooms vengono continuamente valutati e testati durante il ciclo di vita del prodotto.

## <a name="account-security"></a>Sicurezza dell'account

Teams Rooms dispositivi includono un account amministrativo denominato "Amministratore" con una password predefinita. È consigliabile cambiare la password predefinita il prima possibile dopo aver completato la configurazione.

L'account amministratore non è necessario per il corretto funzionamento Teams Rooms dispositivi e può essere rinominato o persino eliminato. Tuttavia, prima di eliminare l'account amministratore, assicurarsi di configurare un account di amministratore locale alternativo configurato prima di rimuovere quello fornito con Teams Rooms dispositivi. Per altre informazioni su come modificare una password per un account Windows locale usando gli strumenti di Windows predefiniti o PowerShell, vedere quanto segue:

- [Cambiare o reimpostare la password Windows password](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

È anche possibile importare account di dominio nel gruppo Windows amministratore locale. È possibile eseguire questa operazione per Azure AD account usando Intune. Per altre informazioni, vedere [Policy CSP – RestrictedGroups](/windows/client-management/mdm/policy-csp-restrictedgroups).

> [!NOTE]
> Se si usano console Crestron, assicurarsi di aggiornare anche la password di amministratore nella console e nel modulo di calcolo. Per altre informazioni, contattare Crestron.

> [!CAUTION]
> Se si elimina o si disabilita l'account amministratore prima di concedere le autorizzazioni di amministratore locale a un altro account locale o di dominio, si potrebbe perdere la possibilità di amministrare il dispositivo Teams Rooms locale. In questo caso, sarà necessario ripristinare le impostazioni originali del dispositivo e completare di nuovo il processo di configurazione.

Non concedere autorizzazioni di amministratore locale all'account Skype utente.

Windows Configuration Designer può essere usato per creare pacchetti Windows 10 di provisioning. Oltre a cambiare la password di amministratore locale, è anche possibile eseguire operazioni come la modifica del nome del computer e la registrazione in Azure Active Directory. Per altre informazioni sulla creazione di un pacchetto Windows di provisioning di Configuration Designer, vedere [Pacchetti di provisioning per Windows 10](/windows/configuration/provisioning-packages/provisioning-packages).

È necessario creare un account di risorsa per ogni dispositivo Teams Rooms in modo che possa accedere a Teams. Con questo account non è possibile usare l'autenticazione a due fattori o a più fattori. Richiedendo un secondo fattore, l'account non sarà in grado di accedere automaticamente all'app Teams Rooms dopo il riavvio. Tuttavia, è possibile abilitare l'autenticazione moderna per una sicurezza aggiuntiva per questo account. Inoltre, è Azure Active Directory criteri di accesso condizionale e criteri di conformità di Intune per proteggere l'account delle risorse. Per altre informazioni, vedere [Accesso](supported-ca-and-compliance-policies.md) condizionale supportato e Criteri di conformità dei dispositivi Intune per Microsoft Teams Rooms e Accesso condizionale e Conformità [di Intune per Microsoft Teams Rooms](conditional-access-and-compliance-for-devices.md)

È consigliabile creare l'account della risorsa in Azure AD, se possibile. Anche se un account sincronizzato può funzionare con Teams Rooms nelle distribuzioni ibride, questi account sincronizzati spesso hanno difficoltà ad accedere a Teams Rooms e possono essere difficili da risolvere. Se si sceglie di usare un servizio federativo di terze parti per autenticare le credenziali per l'account della risorsa, verificare che il provider di `wsTrustResponse` identità di terze parti risponda con l'attributo impostato su `urn:oasis:names:tc:SAML:1.0:assertion`.

## <a name="network-security"></a>Sicurezza di rete

In generale, Teams Rooms ha gli stessi requisiti di rete di qualsiasi client Microsoft Teams client. L'accesso tramite firewall e altri dispositivi di sicurezza è lo stesso per Teams Rooms per qualsiasi altro client Microsoft Teams. Specifiche per Teams Rooms, le categorie elencate come "obbligatorie" per Teams devono essere aperte nel firewall. Teams Rooms anche l'accesso a Windows, Microsoft Store e Microsoft Intune (se si usa Microsoft Intune per gestire i dispositivi). Per l'elenco completo degli INDIRIZZI IP e degli URL necessari per Microsoft Teams Rooms, vedere:

- **Microsoft Teams** [Office 365 URL e intervalli di indirizzi IP](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows aggiorna Configura** [WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft Store** [prerequisiti per l'Microsoft Store per le aziende e l'istruzione](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [endpoint di rete per Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Se si usa il componente Microsoft Teams Rooms servizi gestiti di Microsoft Teams Rooms Premium, è anche necessario assicurarsi che Teams Rooms possa accedere agli URL seguenti:

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

Teams Rooms è configurato per mantenersi automaticamente aggiornato con gli aggiornamenti Windows, inclusi gli aggiornamenti della sicurezza. Teams Rooms gli aggiornamenti in sospeso ogni giorno a partire dalle 2:00 usando un criterio locale pre-impostato. Non è necessario usare altri strumenti per distribuire e applicare Windows aggiornamenti. L'uso di strumenti aggiuntivi per distribuire e applicare gli aggiornamenti può ritardare l'installazione di Windows e quindi portare a una distribuzione meno sicura. L Teams Rooms app viene distribuita usando il Microsoft Store. Se i dispositivi sono concessi in licenza con Microsoft Teams Rooms Standard, le nuove versioni dell'app vengono installate automaticamente durante il processo di applicazione delle patch notturne. Se i dispositivi sono concessi in licenza con Microsoft Teams Rooms Premium e registrati nel servizio gestito Microsoft, le nuove versioni dell'app Teams Rooms vengono installate in base al piano di implementazione definito.

Teams Rooms di rete funzionano con la maggior parte dei protocolli di sicurezza basati su rete 802.1X. Tuttavia, non è possibile testare Teams Rooms tutte le possibili configurazioni di sicurezza di rete. Pertanto, se si verificano problemi di prestazioni che possono essere riconciliati con problemi di prestazioni di rete, potrebbe essere necessario disabilitare questi protocolli se sono configurati nell'organizzazione.

Per prestazioni ottimali dei supporti multimediali in tempo reale, è consigliabile configurare il traffico multimediale Teams in modo da ignorare i server proxy e altri dispositivi di sicurezza di rete. I supporti multimediali in tempo reale sono molto sensibili alla latenza e i server proxy e i dispositivi di sicurezza di rete possono ridurre significativamente la qualità audio e video degli utenti. Inoltre, poiché Teams multimediali sono già crittografati, non esiste alcun vantaggio tangibile dal passaggio del traffico attraverso un server proxy. Per altre informazioni, vedere Networking [up (to the cloud) —](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) Punto di vista di un architetto che illustra i consigli di rete per migliorare le prestazioni dei supporti multimediali con Microsoft Teams e Microsoft Teams Rooms.

> [!IMPORTANT]
> Teams Rooms non supporta i server proxy autenticati.

Teams Rooms non è necessario connettersi a una LAN interna. È consigliabile inserire Teams Rooms in un segmento di rete sicuro con accesso diretto a Internet. Se la rete LAN interna viene compromessa, le opportunità di attacco verso Teams Rooms verranno ridotte.

È consigliabile connettere i dispositivi Teams Rooms a una rete cablata. L'uso di reti wireless su Teams Rooms non è consigliato o certificato. Alcune funzionalità di connettività, ad esempio Wi-Fi Sense, sono disabilitate per impostazione predefinita.

Proximity Join e altre funzionalità Teams Rooms si basano su Bluetooth. Tuttavia, l'implementazione Bluetooth nei dispositivi Teams Rooms non consente la connessione di un dispositivo esterno a un Teams Rooms dispositivo. Bluetooth l'uso della tecnologia su Teams Rooms è attualmente limitato ai beacon pubblicitari e alle connessioni proxy richieste. Il `ADV_NONCONN_INT` tipo di unità dati protocollo (PDU) viene usato nel beacon pubblicitario. Questo tipo di PDU è per i dispositivi non collegabili che pubblicizzano informazioni sul dispositivo di ascolto. Non esiste alcuna associazione Bluetooth dispositivo come parte di queste funzionalità. Ulteriori dettagli sui Bluetooth protocolli sono disponibili nel sito [Web Bluetooth SIG](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/).
