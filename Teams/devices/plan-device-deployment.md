---
title: Pianificare la distribuzione per Teams telefoni cellulari e schermi
ms.author: czawideh
author: cazawideh
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
description: Questo articolo fornisce e offre una panoramica delle attività e dei passaggi per distribuire Teams telefoni e schermi nell'organizzazione.
ms.openlocfilehash: 2ad9840d6ebd1ac6973027dedf6be294704f5326
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2021
ms.locfileid: "61577796"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Pianificare la distribuzione per Teams telefoni cellulari e schermi

Una distribuzione riuscita di Teams telefoni e Teams display inizia con la pianificazione. Questo articolo illustra le attività e i passaggi per distribuire questi dispositivi nell'organizzazione. Fornisce anche indicazioni sull'uso dei dispositivi, sulle licenze, sull'integrazione con l'ambiente, i punti di contatto e la gestione.

> [!TIP]
> [L Microsoft 365 Adoption Hub](https://adoption.microsoft.com/) è un ottimo punto di partenza per iniziare il tuo percorso di adozione con Microsoft Teams.

## <a name="task-1-what-are-your-deployment-objectives"></a>Attività 1: Quali sono gli obiettivi di distribuzione?

La pianificazione dell'implementazione di Teams telefoni e schermi nell'organizzazione inizia con gli obiettivi di distribuzione. Teams dispositivi supportano il lavoro ibrido nelle sale riunioni, negli uffici e in altri spazi funzionali. Dovrai determinare dove verranno usati questi dispositivi e da chi.

### <a name="objective-identify-your-device-personas"></a>Obiettivo: Identificare le persone del dispositivo

Teams telefoni e schermi si adattano a uno dei due tipi di persona seguenti: 

- Dispositivi personali
- Dispositivi con spazio condiviso

I dispositivi personali e condivisi hanno ruoli e utilizzi diversi. 

**Dispositivi personali:** 

- In genere assegnato a un utente, connesso con l'account dell'utente e abilitato con una licenza Teams per accedere al servizio.
- Si pensi ai dispositivi personali come a una relazione uno-a-uno, con un dispositivo per ogni utente.
- Può essere associato al client desktop Teams e usare caratteristiche come Better Together
- Può connettersi a un auricolare, cablato o wireless
- Altre funzionalità nei dispositivi personali includono l'hot desking e la schermata home. 

**Dispositivi con spazio condiviso:**

- Eseguire una funzione specifica, ad esempio un telefono di area comune o un dispositivo della sala riunioni e richiedere un account dedicato e una licenza per le funzionalità per accedere al servizio.
- Si pensi ai dispositivi condivisi come a una relazione uno-a-molti: un dispositivo condiviso da molti utenti.
- Distribuito in spazi condivisi come sale riunioni, aree di ricezione o piani di produzione. 
- Le interfacce utente sono specifiche per la funzione, ad esempio l'interfaccia utente dell'area comune Telefono o la sala riunioni, dipendono dalla funzione e dal posizionamento del dispositivo condiviso.
- Richiedere la configurazione e la protezione avanzata facoltativa per assicurarsi che le impostazioni non siano modificate o per impedire la disconnessione dell'account. 
- Altre funzionalità nei dispositivi con spazio condiviso includono la ricerca nei telefoni dell'area comune e l'hot desking con timeout di inattività

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>Obiettivo: Quanti dispositivi di spazio personale e condiviso sono necessari?

Dopo aver identificato i dispositivi personali, è necessario determinare quali dispositivi certificati usare e quanti di essi sono necessari. Per prendere questa decisione, prendere in considerazione le domande seguenti: 

- Quanti dispositivi personali sono necessari e chi ne avrà uno?
- Quante sale o spazi richiedono dispositivi condivisi? Ogni spazio avrà lo stesso tipo di dispositivo? 
- I dispositivi dovranno soddisfare requisiti specifici?
    - Alcuni esempi includono le dimensioni dello schermo, il fattore di forma e il produttore o il modello? Per un elenco di telefoni e schermi certificati, vedere Microsoft Teams [dispositivi certificati.](teams-ip-phones.md)
-  Hai bisogno di Teams telefoni o Teams display? Per un elenco delle funzionalità supportate dai telefoni Teams, vedere Telefoni per [Microsoft Teams](phones-for-teams.md#features-supported-by-teams-phones) e per un elenco delle caratteristiche supportate dagli schermi Teams, vedere Microsoft Teams [schermi](teams-displays.md#features-supported-by-teams-displays).
- Sono disponibili dispositivi sufficienti per i nuovi utenti o un processo per i nuovi ordini e la consegna?
- Sono disponibili dispositivi di riserva per la manutenzione o in caso di problemi hardware? La possibilità di scambiare rapidamente un dispositivo evita interruzioni dell'esperienza utente.

## <a name="task-2-what-are-your-licensing-requirements"></a>Attività 2: Quali sono i requisiti di licenza? 

Ora si sa quanti dispositivi sono necessari, il passaggio successivo consiste nel determinare quante licenze sono necessarie. Teams telefoni e schermi richiedono licenze per accedere a Microsoft Teams e Microsoft 365.

I dispositivi condivisi e personali dovranno avere licenze diverse. Per i dispositivi personali, è possibile usare le licenze assegnate agli account utente. I dispositivi condivisi hanno bisogno di licenze specifiche per la loro funzione. Per telefoni e schermi, le licenze applicabili sono la licenza [Telefono per](../set-up-common-area-phones.md#step-1---buy-the-licenses) Microsoft Teams e la licenza [Microsoft Teams Rooms Standard.](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices)

Per altre informazioni e per confrontare le opzioni di licenza, vedere Microsoft 365 [licenze.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 

## <a name="task-3-what-are-your-dependencies"></a>Attività 3: Quali sono le dipendenze? 

### <a name="objective-plan-your-device-identities"></a>Obiettivo: Pianificare le identità del dispositivo

Le identità consentono ai dispositivi di accedere Microsoft 365 servizi e dovrebbero semplificare l'individuazione, la gestione e la connessione dei dispositivi all'interno dell'organizzazione. A questo scopo, tenere presente quanto segue quando si pianificano le identità dei dispositivi:

- Nomi delle entità utente e relativo formato e dominio
- Nomi visualizzati
- Individuabilità della rubrica
- Tipi di dispositivo spazio personale e condiviso
- Confronto tra gruppo e licenze assegnate dall'utente

### <a name="objective-review-conditional-access-policies"></a>Obiettivo: Esaminare i criteri di accesso condizionale

Azure Active Directory criteri di accesso condizionale sono requisiti aggiuntivi che devono essere soddisfatti prima di poter accedere a un dispositivo.

Durante la pianificazione della distribuzione

- Esaminare i criteri di accesso condizionale esistenti che potrebbero influire Teams telefoni e schermi. È possibile eseguire questa operazione nell'Azure AD di amministrazione usando lo strumento [What If](/azure/active-directory/conditional-access/what-if-tool) e i log [di accesso](/azure/active-directory/reports-monitoring/concept-sign-ins)

- Pianificare nuove regole, se necessario

- Usare le funzionalità di accesso condizionale, ad esempio i filtri di dispositivo, per applicare regole Teams telefoni e schermi.

>[!NOTE]
>Esistono alcuni criteri di accesso condizionale non supportati da dispositivi Android. Per istruzioni e procedure consigliate, vedere Procedure consigliate per l'autenticazione per Teams [dispositivi Android.](authentication-best-practices-for-android-devices.md)

## <a name="task-4-prepare-your-environment"></a>Attività 4: Preparare l'ambiente

### <a name="objective-plan-network-basics"></a>Obiettivo: Pianificare le nozioni di base sulla rete

Teams Telefono dispositivi e schermi richiedono l'accesso a Internet per connettersi Teams e funzionare come previsto. Per prepararsi alla distribuzione della rete, tenere presente quanto segue:

- L'infrastruttura di rete ha una capacità sufficiente? Valutare la possibilità di cambiare porta, punti di accesso wireless e altre coperture.
- Se si usano VLAN e DHCP, gli ambiti vengono ridimensionati di conseguenza?
- Valutare e testare i percorsi di rete da cui i dispositivi vengono distribuiti Microsoft 365. 
- Aprire le porte e gli URL del firewall necessari per Microsoft 365 come da indicazioni.
- Esaminare e testare i requisiti e la configurazione di E911 per l'accuratezza e la conformità della posizione. 
- Evitare di usare un server proxy e ottimizzare i percorsi multimediali per l'affidabilità e la qualità.

### <a name="objective-physical-considerations"></a>Obiettivo: Considerazioni fisiche

Considerare gli spazi fisici in cui Teams telefoni e schermi.

Gli aspetti chiave includono

- **Alimentazione:** Hai abbastanza prese elettriche? Se il dispositivo ha bisogno di una fonte di alimentazione esterna, quanto vicino è possibile posizionarlo su una presa?
- **Posizionamento del dispositivo:** Dove si trova fisicamente il dispositivo? Esaminare supporti da tavolo, supporti a parete e altri accessori del produttore originale di apparecchiature (OEM).
- **Sicurezza:** Il dispositivo deve essere bloccato in determinati spazi?
- **Accessibilità:** Il dispositivo soddisfa i requisiti di accessibilità dell'utente principale? Considerare la posizione, la lunghezza del cavo e l'usabilità del ricevitore o dell'auricolare.

### <a name="task-5-how-will-you-manage-deployed-devices"></a>Attività 5: Come si gestiscono i dispositivi distribuiti?

Teams telefoni e schermi sono gestiti da due a tre portali Microsoft 365 e dai rispettivi moduli di PowerShell: 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory di amministrazione

Usare l'Azure AD di amministrazione per gestire

- Tutte le attività correlate all'identità per Teams telefoni e schermi
- Criteri di accesso condizionale 
- Reimpostazione della password

#### <a name="teams-admin-center"></a>Teams di amministrazione

Usare l'Teams di amministrazione per gestire

- [Impostazioni del dispositivo per Teams](../business-voice/manage-devices.md)
- [Profili di configurazione](device-management.md#use-configuration-profiles-in-teams)
- [Tagging del dispositivo](manage-device-tags.md)
- [Accesso remoto e disconnessione](remote-sign-in-and-sign-out.md)
- Analisi delle chiamate  
- Firmware
- Risoluzione dei problemi e download dei log

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Endpoint Manager di amministrazione (se si usa Intune per la gestione dei dispositivi)

Usare l'Endpoint Manager di amministrazione per gestire: 

- Criteri di conformità dei dispositivi
- Restrizioni di registrazione
- Identificatori di dispositivo aziendali
- Filtri di dispositivo
