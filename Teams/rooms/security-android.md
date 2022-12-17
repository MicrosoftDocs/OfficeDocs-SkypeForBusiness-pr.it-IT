---
title: Sicurezza di Microsoft Teams per Android
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
description: Informazioni su come proteggere Microsoft Teams per dispositivi Android.
ms.openlocfilehash: 044ff85a39058df85a1f132aaac08bb1d87c6c95
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438560"
---
# <a name="microsoft-teams-for-android-security"></a>Sicurezza di Microsoft Teams per Android

Questo articolo non illustra i dispositivi Android configurati per la modalità dispositivo dedicata da Microsoft Endpoint Manager. I dispositivi Teams Android vengono eseguiti in modalità tutto schermo da progettazione. Per informazioni su Chiosco Android, vedi [Registrazione del dispositivo dedicato ad Android Enterprise](/mem/intune/enrollment/android-kiosk-enroll).

Microsoft collabora con i propri partner OEM per offrire una soluzione sicura da progettazione e personalizzabile in base alle esigenze dei clienti. Questo articolo descrive molte delle funzionalità di sicurezza disponibili nei dispositivi Android di Teams e il nostro approccio. È suddiviso in quattro sezioni chiave per facilitare la navigazione.

> [!NOTE]
> I dispositivi Android di Microsoft Teams non devono essere trattati come un tipico dispositivo Android. I dispositivi Teams Android sono accessori appositamente progettati per l'uso con Teams e i rispettivi casi d'uso. Questo articolo si applica solo ai dispositivi certificati e dedicati di Microsoft Teams che eseguono il sistema operativo Android. I dispositivi certificati per Teams possono essere acquistati solo da fornitori OEM certificati. Per informazioni sui dispositivi Android certificati da Microsoft Teams, vedere [Dispositivi Android certificati da Microsoft Teams](/microsoftteams/devices/teams-ip-phones).

Per informazioni sulla sicurezza in Teams Rooms nei dispositivi Windows, vedi [Microsoft Teams Rooms sulla sicurezza di Windows](security-windows.md).

## <a name="software-security"></a>Sicurezza del software

### <a name="android-kiosk-mode"></a>Modalità tutto schermo Android

I dispositivi Teams Android sono bloccati per eseguire solo le applicazioni approvate eseguendo il dispositivo in modalità tutto schermo Android. La modalità tutto schermo disabilita l'accesso a tutte le funzionalità di avvio del programma di avvio e contribuisce a proteggere il dispositivo in modo che le applicazioni autorizzate vengano avviate sul dispositivo.  

| Nome applicazione            | Descrizione applicazione                   |
|-----------------------------|-------------------------------------------|
| Microsoft Teams Android App | Applicazione dispositivo Microsoft Teams        |
| Microsoft Teams Amministrazione Agent | Gestione remota dell'interfaccia di amministrazione di Teams      |
| Portale aziendale Intune       | Registrazione dispositivo, registrazione & accesso |
| Agente partner OEM           | App Impostazioni dispositivo & agente partner OEM   |

Per impostazione predefinita, l'app Microsoft Teams per Android verrà avviata all'avvio in modalità tutto schermo Android e non fornisce all'utente alcun accesso al sistema operativo o ai componenti al di fuori dell'esperienza utente di Teams designata.

### <a name="application-code-signing"></a>Firma del codice dell'applicazione

Tutte le applicazioni Microsoft e OEM sono firmate con codice. La firma del codice aiuta a convalidare che il software in esecuzione su un dispositivo sia originale da Microsoft e dai nostri partner hardware. La firma del codice tenta anche di convalidare l'integrità del software in esecuzione nel dispositivo, in modo che solo il software originale possa avviarsi ed eseguire.  

### <a name="third-party-applications"></a>Applicazioni di terze parti

I dispositivi certificati per Teams non hanno Google Play Store, Amazon App Store o Google Play Services, installati da progettazione. In questo modo si garantisce che non sia possibile installare applicazioni di terze parti dallo store in un dispositivo.  

### <a name="android-debug-bridge"></a>Bridge di debug di Android

Il bridge di debug Android (ADB) è disabilitato dalla progettazione in tutti i dispositivi Android di Teams che eseguono software di rilascio. ADB è uno strumento da riga di comando che consente agli amministratori di eseguire funzioni sui dispositivi basati su Android e consente l'installazione di app, l'accesso alla shell del dispositivo e altre funzioni di amministrazione.  

### <a name="file-system-encryption"></a>Crittografia del file system

I dispositivi Android di Teams devono supportare la crittografia basata su Android e possono essere applicati usando i criteri di conformità di Microsoft Endpoint Manager. Per informazioni sui criteri di conformità di Endpoint Manager [Usare i criteri di conformità di Endpoint Manager per impostare le regole per i dispositivi gestiti con Intune](/mem/intune/protect/device-compliance-get-started).

### <a name="android-os-version"></a>Versione del sistema operativo Android

I dispositivi Teams Android eseguono versioni supportate di Android. Il sistema operativo Android è gestito da partner OEM, unito al firmware certificato di Teams e quindi inserito nei dispositivi dall'interfaccia di amministrazione di Teams. Per informazioni sulle versioni Android in esecuzione sui dispositivi Android di Teams, vedere [Dispositivi Android certificati da Microsoft Teams](/microsoftteams/devices/teams-ip-phones).

### <a name="android-security-updates"></a>Aggiornamenti della sicurezza di Android

I fornitori OEM, nell'ambito del processo di aggiornamento del firmware, incorporano le basi di riferimento appropriate per gli aggiornamenti della sicurezza Android per garantire che il sistema operativo di base sia protetto. Mantenere i dispositivi aggiornati regolarmente è importante per assicurarsi che gli aggiornamenti della sicurezza Android appropriati siano in esecuzione sui dispositivi. Per ulteriori informazioni, fai riferimento al produttore del dispositivo.

### <a name="account-security"></a>Sicurezza dell'account

I dispositivi Android di Teams sono creati intorno a due tipi di account che consentono il corretto funzionamento di un dispositivo.

- Account amministratore del dispositivo locale

- Account utente o della risorsa  

Anche i dispositivi Android di Teams sono compatibili con alcuni criteri di accesso condizionale, che possono essere usati come livelli aggiuntivi di sicurezza per l'accesso dei dispositivi. Per le procedure consigliate e i criteri di accesso condizionale supportati, vedere [Criteri di conformità per l'accesso condizionale supportati](/microsoftteams/rooms/supported-ca-and-compliance-policies).

### <a name="local-device-administrator-account"></a>Account amministratore del dispositivo locale

I dispositivi Teams Android includono un account amministrativo per accedere alle impostazioni del dispositivo, il server Web locale, se installato, e le impostazioni specifiche dell'OEM.

Gli elementi iniziali di configurazione e configurazione del dispositivo, ad esempio il nome utente e la password predefiniti per questo account, possono essere ottenuti dal produttore del dispositivo.

> [!CAUTION]
> Assicurati di cambiare la password dell'amministratore del dispositivo locale il prima possibile.  

> [!TIP]
> L'interfaccia di amministrazione di Teams può essere usata per cambiare la password di amministratore del dispositivo locale di un dispositivo Android connesso a Teams applicando un profilo di configurazione. È consigliabile questo approccio dopo l'accesso iniziale del dispositivo per proteggere le funzionalità elevate di un dispositivo Android. Le funzionalità elevate possono includere le impostazioni dei dispositivi e i portali di amministrazione Web, se supportati.

### <a name="user-or-resource-account"></a>Account utente o della risorsa

I dispositivi Teams android richiedono l'uso di un utente, o di un account di risorse dedicato, per accedere a Microsoft 365. Tentiamo di proteggere questi account in modi specifici, a seconda che si tratti di un normale account utente per un dispositivo personale o di un account di risorse per un dispositivo condiviso. Per altre informazioni, vedere [Creare e configurare account di risorse per sale e dispositivi condivisi](/microsoftteams/rooms/with-office-365).

### <a name="device-updates"></a>Aggiornamenti dei dispositivi

I dispositivi Android di Teams sono configurati per scaricare gli aggiornamenti certificati da Microsoft dall'interfaccia di amministrazione di Teams non appena disponibili. Questi possono essere inviati automaticamente o manualmente richiamati da un amministratore. Strumenti di terze parti dei nostri partner OEM sono disponibili anche per eseguire questa funzione, se necessario. I dispositivi Android di Teams possono installare gli aggiornamenti dopo l'orario di lavoro per evitare l'impatto sugli utenti. Le pianificazioni fuori orario possono essere configurate nell'interfaccia di amministrazione di Teams o usando strumenti di terze parti dei partner OEM.

> [!IMPORTANT]
> Microsoft consiglia la gestione del firmware per tutti i dispositivi Android di Teams viene eseguita tramite l'interfaccia di amministrazione di Teams.

## <a name="network-security"></a>Sicurezza della rete

I dispositivi Teams Android hanno gli stessi requisiti di rete di qualsiasi client Microsoft Teams, incluso l'accesso attraverso firewall e altri dispositivi di sicurezza. In particolare, le categorie elencate come **obbligatorie** per Teams devono essere aperte sul firewall insieme ad altri servizi di supporto elencati di seguito. Per l'elenco completo di INDIRIZZI IP e URL necessari per i dispositivi Teams Android, vedere:

- Microsoft Teams, Exchange Online, SharePoint Online, Microsoft 365 Common e Office Online [Office 365 URL e intervallo di indirizzi IP](/microsoft-365/enterprise/urls-and-ip-address-ranges)

- Endpoint di rete di Microsoft Intune [per Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

I dispositivi Android di Teams funzionano con la maggior parte dei protocolli di sicurezza 802.1X e di altri protocolli di sicurezza basati sulla rete. Tuttavia, non è possibile testare i dispositivi Teams Android con tutte le configurazioni di sicurezza di rete. Pertanto, se si verificano problemi di prestazioni che possono essere rilevati da problemi di prestazioni di rete, potrebbe essere necessario disabilitare questi protocolli se sono configurati nell'organizzazione o contattare il partner OEM per assistenza.

Per ottenere prestazioni ottimali dai supporti in tempo reale, è consigliabile configurare il traffico multimediale di Teams in modo da ignorare i server proxy e altri dispositivi di sicurezza di rete. I supporti in tempo reale sono sensibili alla latenza della rete, che può essere causata da server proxy e altri dispositivi di sicurezza di rete. La latenza della rete può ridurre significativamente la qualità audio e video degli utenti. Per altre informazioni, vedere Creazione di reti [(nel cloud): punto di vista di un architetto](/microsoft-365/solutions/networking-design-principles) che discute dei suggerimenti di rete per migliorare le prestazioni dei supporti con Microsoft Teams.

I dispositivi Android di Teams usano comunicazioni crittografate e l'autenticazione degli endpoint su Internet. I dispositivi Android di Teams usano TLS 1.2+.  

> [!IMPORTANT]
> I dispositivi Android di Teams non supportano server proxy autenticati o restrizioni del tenant. Contatta il partner OEM per informazioni sul supporto del proxy.

I dispositivi Android di Teams non devono connettersi a una LAN interna. Valutare l'inserimento di dispositivi Teams Android in un segmento di rete sicuro con accesso diretto a Internet. Ad esempio, i telefoni di Teams possono essere distribuiti su una VLAN vocale. Se la LAN interna viene compromessa, le opportunità del vettore di attacco verso i dispositivi Teams Android verranno ridotte implementando questa separazione della rete.

Si consiglia vivamente di connettere i dispositivi Teams Android a una rete cablata. L'uso di reti wireless richiede un'attenta pianificazione e valutazione per un'esperienza ottimale.

L'unione in prossimità, Better Together, Teams Cast e l'associazione dei pannelli di Teams si basano sul Bluetooth. L'uso della tecnologia Bluetooth su Teams Rooms nei dispositivi Android è attualmente limitato agli annunci beacon e alle connessioni proximal richieste. Il `ADV_NONCONN_INT` tipo di unità di dati del protocollo (PDU) viene utilizzato nel advertising beacon. Questo tipo di PDU è per le informazioni pubblicitarie sui dispositivi non collegabili al dispositivo di ascolto. Non esiste alcuna associazione di dispositivi Bluetooth nell'ambito di queste funzionalità. Ulteriori dettagli sui protocolli Bluetooth sono disponibili sul sito Web Bluetooth SIG.

I telefoni e i display di Teams offrono la funzionalità di associazione Bluetooth per l'associazione con le cuffie tramite il profilo Bluetooth Hands-Free.

Per altre informazioni sulla sicurezza in Microsoft Teams, vedere [Sicurezza e Microsoft Teams](/microsoftteams/teams-security-guide).  
