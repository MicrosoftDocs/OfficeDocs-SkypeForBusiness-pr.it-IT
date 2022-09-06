---
title: Pianificare la distribuzione per i dispositivi telefonici e gli schermi di Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: tony.woodruff
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
search.appverid: MET150
description: Questo articolo fornisce una panoramica delle attività e dei passaggi per distribuire i telefoni e gli schermi di Teams nell'organizzazione.
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
ms.openlocfilehash: fb9b560f56ece49ddae9f15899a118596a31c38f
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606845"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Pianificare la distribuzione per i dispositivi telefonici e gli schermi di Teams

La corretta distribuzione dei dispositivi telefonici di Teams e dei display di Teams inizia con la pianificazione. Questo articolo illustra le attività e i passaggi per distribuire questi dispositivi nell'organizzazione. Fornisce anche indicazioni sull'utilizzo dei dispositivi, le licenze, l'integrazione con l'ambiente, i touchpoint e la gestione.

> [!TIP]
> [L'Hub di Adozione di Microsoft 365](https://adoption.microsoft.com/) è il posto ideale per iniziare il percorso di adozione con Microsoft Teams.

## <a name="task-1-what-are-your-deployment-objectives"></a>Attività 1: Quali sono gli obiettivi della distribuzione?

La pianificazione dell'implementazione dei telefoni e degli schermi di Teams nell'organizzazione inizia con gli obiettivi di distribuzione. I dispositivi Teams supportano il lavoro ibrido in sale riunioni, uffici e altri spazi funzionali. Dovrai determinare dove verranno usati questi dispositivi e da chi.

### <a name="objective-identify-your-device-personas"></a>Obiettivo: Identificare i personaggi del dispositivo

I telefoni e gli schermi di Teams si adattano a uno dei due utenti tipo: 

- Dispositivi personali
- Dispositivi per lo spazio condiviso

I dispositivi personali e condivisi hanno ruoli e usi diversi. 

**Dispositivi personali:** 

- In genere assegnato a un utente, connesso con l'account dell'utente e abilitato con una licenza di funzionalità di Teams per accedere al servizio.
- I dispositivi personali hanno una relazione uno-a-uno, con un dispositivo per un utente.
- Può essere abbinato al client desktop di Teams e usare funzionalità come Better Together
- Può connettersi a un auricolare, cablato o wireless
- Altre funzionalità sui dispositivi personali includono hot desking e schermata home. 

**Dispositivi per lo spazio condiviso:**

- Eseguire una funzione specifica, ad esempio un telefono dell'area comune o un dispositivo della sala riunioni e richiedere un account dedicato e una licenza di funzionalità per accedere al servizio.
- I dispositivi condivisi hanno una relazione uno-a-molti: un dispositivo condiviso da molti utenti.
- Distribuito in spazi condivisi come sale riunioni, aree di ricevimento o pavimenti di produzione. 
- Le interfacce utente sono specifiche per la loro funzione, ad esempio l'interfaccia utente del telefono area comune o l'interfaccia utente della sala riunioni dipendono dalla funzione e dal posizionamento del dispositivo condiviso.
- Richiedere la configurazione e la protezione avanzata facoltativa per assicurarsi che le impostazioni non vengano modificate o per impedire all'account di disconnettersi. 
- Altre funzionalità nei dispositivi di spazio condiviso includono la ricerca nei telefoni dell'area comune e l'hot desking con timeout di inattività

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>Obiettivo: Quanti dispositivi di spazio personali e condivisi ti servono?

Ora che hai identificato i personaggi del dispositivo, devi determinare quali dispositivi certificati vuoi usare e quanti di essi ti servono. Per aiutarti a prendere questa decisione, prendi in considerazione le domande seguenti: 

- Quanti dispositivi personali sono necessari e chi ne avrà uno?
- Quanti ambienti o spazi richiedono dispositivi condivisi? Ogni spazio avrà lo stesso tipo di dispositivo? 
- I tuoi dispositivi dovranno soddisfare requisiti specifici?
    - Gli esempi includono le dimensioni dello schermo, il fattore di forma e il produttore o modello? Per un elenco di telefoni e schermi certificati, vedere [Dispositivi certificati per Microsoft Teams](teams-ip-phones.md).
-  Ti servono i telefoni o gli schermi di Teams? Per un elenco delle funzionalità supportate dai telefoni di Teams, vedere [Telefoni per Microsoft Teams](phones-for-teams.md#features-supported-by-teams-phones). Per un elenco delle funzionalità supportate dagli schermi di Teams, vedere [Schermi di Microsoft Teams](teams-displays.md#features-supported-by-teams-displays).
- Hai un numero di dispositivi sufficiente per i nuovi utenti o un processo per i nuovi ordini e la consegna?
- Avrai a disposizione dispositivi di riserva per la manutenzione o se si verificano problemi hardware? La possibilità di scambiare rapidamente un dispositivo impedisce interruzioni dell'esperienza utente.

## <a name="task-2-what-are-your-licensing-requirements"></a>Attività 2: Quali sono i requisiti di licenza? 

Ora che sai quanti dispositivi ti servono, il passaggio successivo consiste nel determinare quante licenze sono necessarie. I telefoni e gli schermi di Teams richiedono licenze per accedere a Microsoft Teams e Microsoft 365.

I dispositivi condivisi e personali richiedono licenze diverse. Per i dispositivi personali, è possibile usare le licenze assegnate agli account utente. I dispositivi condivisi devono avere licenze specifiche per la loro funzione. Per telefoni e schermi, le licenze applicabili sono [la licenza Common Area Phone per Microsoft Teams](../set-up-common-area-phones.md#step-1---buy-the-licenses) e una [licenza di Microsoft Teams Rooms](../rooms/rooms-licensing.md).

Per altre informazioni e per confrontare le opzioni di licenza, vedere [Piani di licenza di Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).

## <a name="task-3-what-are-your-dependencies"></a>Attività 3: Quali sono le dipendenze? 

### <a name="objective-plan-your-device-identities"></a>Obiettivo: Pianificare le identità del dispositivo

Le identità consentono ai dispositivi di accedere ai servizi di Microsoft 365 e dovrebbero semplificare l'individuazione, la gestione e la connessione dei dispositivi all'interno dell'organizzazione. A tale scopo, quando si pianificano le identità dei dispositivi, tenere presente quanto segue:

- Nomi delle entità utente e formato e dominio
- Nomi visualizzati
- Individuabilità della rubrica
- Tipi di dispositivi con spazi personali e condivisi
- Licenze assegnate a gruppi e utenti

### <a name="objective-review-conditional-access-policies"></a>Obiettivo: Rivedere i criteri di accesso condizionale

I criteri di accesso condizionale di Azure Active Directory sono requisiti aggiuntivi che devono essere soddisfatti prima che un dispositivo possa eseguire l'accesso.

Durante la pianificazione della distribuzione

- Esaminare i criteri di accesso condizionale esistenti che potrebbero influire sui telefoni e gli schermi di Teams. È possibile eseguire questa operazione nel Centro Amministrazione di Azure AD usando [lo strumento What If](/azure/active-directory/conditional-access/what-if-tool) e [i log di accesso](/azure/active-directory/reports-monitoring/concept-sign-ins)

- Pianificare nuove regole, se necessario

- Usare le funzionalità di accesso condizionale come i filtri dei dispositivi per applicare regole ai telefoni e agli schermi di Teams.

>[!NOTE]
>Alcuni criteri di accesso condizionale non sono supportati da dispositivi Android. Per indicazioni e procedure consigliate, vedere Dispositivi Android, vedere [Procedure consigliate per l'autenticazione per i dispositivi Teams Android](authentication-best-practices-for-android-devices.md).

## <a name="task-4-prepare-your-environment"></a>Attività 4: Preparare l'ambiente

### <a name="objective-plan-network-basics"></a>Obiettivo: Pianificare i concetti di base della rete

I dispositivi e gli schermi di Teams Phone richiedono l'accesso a Internet per connettersi a Teams e funzionare come previsto. Per preparare la rete per la distribuzione, tenere presente quanto segue:

- La tua infrastruttura di rete ha una capacità sufficiente? Valuta la possibilità di cambiare porte, punti di accesso wireless e altri tipi di copertura.
- Se si usano le reti VLAN e DHCP, le dimensioni degli ambiti sono adeguate?
- Valuta e testa i percorsi di rete da cui i dispositivi vengono distribuiti a Microsoft 365. 
- Aprire le porte del firewall e gli URL necessari per Microsoft 365 come da istruzioni.
- Rivedere e testare i requisiti e la configurazione di E911 per verificare la precisione e la conformità della posizione. 
- Evitare di usare un server proxy e ottimizzare i percorsi multimediali per l'affidabilità e la qualità.

### <a name="objective-physical-considerations"></a>Obiettivo: Considerazioni fisiche

Considerare gli spazi fisici in cui verranno usati i telefoni e gli schermi di Teams.

Gli aspetti principali includono

- **Potere:** Hai abbastanza prese elettriche? Se il dispositivo necessita di una fonte di alimentazione esterna, quanto puoi posizionarla su una presa?
- **Posizionamento del dispositivo:** Dove sarà fisicamente il tuo dispositivo? Rivedi i supporti della scrivania, i montaggi a parete e altri accessori dell'OEM (Original Equipment Manufacturer).
- **Sicurezza:** Il dispositivo deve essere bloccato in determinati spazi?
- **Accessibilità:** Il dispositivo soddisfa i requisiti di accessibilità del suo utente principale? Considera la posizione, la lunghezza del cavo e l'usabilità del ricevitore o del visore VR.

### <a name="task-5-how-will-you-manage-deployed-devices"></a>Attività 5: Come gestirai i dispositivi distribuiti?

I telefoni e gli schermi di Teams sono gestiti da due a tre portali di Microsoft 365 e i rispettivi moduli PowerShell: 

#### <a name="azure-active-directory-admin-center"></a>Centro Amministrazione Azure Active Directory

Usare il Centro Amministrazione Azure AD per gestire

- Tutte le attività correlate all'identità per i telefoni e gli schermi di Teams
- Criteri di accesso condizionale 
- Reimpostazione della password

#### <a name="teams-admin-center"></a>Teams Amministrazione Center

Usare Teams Amministrazione Center per gestire

- [Impostazioni dei dispositivi per Teams](../business-voice/manage-devices.md)
- [Profili di configurazione](device-management.md#use-configuration-profiles-in-teams)
- [Aggiunta di tag al dispositivo](manage-device-tags.md)
- [Accesso remoto e disconnessione](remote-sign-in-and-sign-out.md)
- Analisi delle chiamate  
- Firmware
- Risoluzione dei problemi e download dei log

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Centro Endpoint Manager Amministrazione (se usi Intune per la gestione dei dispositivi)

Usare il Centro Endpoint Manager Amministrazione per gestire: 

- Criteri di conformità dei dispositivi
- Restrizioni di registrazione
- Identificatori dei dispositivi aziendali
- Filtri dispositivo
