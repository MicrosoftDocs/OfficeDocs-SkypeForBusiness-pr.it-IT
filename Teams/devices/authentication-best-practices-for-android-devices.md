---
title: Procedure consigliate per l'autenticazione per i dispositivi Android
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Guida alle procedure consigliate per l'autenticazione Teams dispositivi Android.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0ff320688d7afc583e1e806803349fb3d07ceb0c
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767209"
---
# <a name="authentication-best-practices-for-teams-android-devices"></a>Procedure consigliate per l'autenticazione Teams dispositivi Android

Questo articolo fornisce indicazioni generali e procedure consigliate per la distribuzione dei criteri di autenticazione per Teams telefoni e dispositivi di chiamata.

>[!NOTE]
>L'accesso condizionale richiede Azure Active Directory (Azure AD) Premium abbonamento.

>[!NOTE]
>I criteri per i dispositivi mobili Android potrebbero non essere applicabili Teams dispositivi Android.


## <a name="personal-and-shared-devices"></a>Dispositivi personali e condivisi

I Teams condivisi, come i dispositivi delle sale riunioni o i telefoni dell'area comune, non possono usare gli stessi requisiti per la registrazione e la conformità che in genere vengono applicati ai dispositivi personali. L'applicazione dei requisiti di autenticazione dei dispositivi personali ai dispositivi condivisi causerà i problemi di accesso seguenti:

1.  **I dispositivi vengono disconnessi a causa dei criteri per le password**

Gli account usati nei Teams hanno un criterio di scadenza password. A differenza degli utenti, gli account usati con i dispositivi condivisi non hanno un utente designato per aggiornarli e ripristinarli a uno stato valido alla scadenza delle password. Se l'organizzazione richiede la scadenza e la reimpostazione periodica delle password, questi account smetteranno di funzionare nei dispositivi Teams finché un amministratore di Teams non reimposta la password ed esegue di nuovo l'accesso.

2.  **I dispositivi non riescono ad accedere a causa dei criteri di accesso condizionale**

I dispositivi condivisi non sono conformi ai criteri Azure AD di accesso condizionale per gli account utente o i dispositivi personali. Se i dispositivi condivisi sono raggruppati con account utente o dispositivi personali per un criterio di accesso condizionale, l'accesso avrà esito negativo.

Ad esempio, se è necessaria l'autenticazione a più fattori per l'accesso Teams, è necessario l'intervento dell'utente per completare l'autenticazione. I dispositivi condivisi non supportano l'autenticazione a più fattori. Allo stesso modo, se l'account è configurato per eseguire di nuovo l'autenticazione ogni X giorni, un dispositivo condiviso non può risolvere il problema senza l'intervento dell'utente.

## <a name="best-practices-for-teams-shared-device-deployments"></a>Procedure consigliate per le Teams di dispositivi condivisi

Microsoft consiglia le impostazioni seguenti quando si distribuiscono Teams dispositivi nell'organizzazione.

### <a name="password-policy"></a>**Criteri password**

Teams dispositivi condivisi devono usare un [account Exchange risorsa.](/exchange/recipients-in-exchange-online/manage-resource-mailboxes) Questi account possono essere sincronizzati da Active Directory o creati direttamente in Azure AD. I criteri di scadenza delle password per gli utenti si applicano anche agli account usati Teams dispositivi condivisi.

Per evitare interruzioni causate da criteri di scadenza delle password, impostare i criteri di scadenza delle password per i dispositivi condivisi in modo che non scadano mai.

A partire da Teams dispositivi CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams versione 1449/1.0.94.2021022403 per telefoni Teams) e [CY2021 Aggiornamento #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams versione 1449/1.0.96.2021051904 per Microsoft Teams Rooms in Android), gli amministratori del tenant possono accedere ai dispositivi Teams in remoto. Non condividere le password con i tecnici per configurare i dispositivi. Gli amministratori possono usare l'accesso remoto per emettere codici di verifica e quindi accedere a questi dispositivi dall'Teams di amministrazione.

Per altre informazioni, vedere [Provisioning remoto e accesso per Teams dispositivi Android.](/MicrosoftTeams/devices/remote-provision-remote-login) 

### <a name="conditional-access-policies"></a>**Criteri di accesso condizionale**

Azure AD l'accesso condizionale imposta requisiti aggiuntivi che i dispositivi devono soddisfare per poter accedere. Per Teams, vedere le indicazioni seguenti per determinare se sono stati creati i criteri appropriati. Per una panoramica dell'accesso condizionale, vedere [Che cos'è l'accesso condizionale.](/azure/active-directory/conditional-access/overview)

### <a name="multi-factor-authentication"></a>Autenticazione a più fattori

Gli account per i dispositivi condivisi sono collegati a una sala o a uno spazio fisico, invece che a un account utente. Poiché i dispositivi condivisi non supportano l'autenticazione a più fattori, escludere i dispositivi condivisi dai criteri di autenticazione a più fattori.

>[!TIP]
>Usare una [posizione denominata o](/azure/active-directory/conditional-access/location-condition) richiedere un dispositivo [conforme](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) per proteggere i dispositivi condivisi.

### <a name="location-based-access-with-named-locations"></a>Accesso in base alla posizione con posizioni denominate

Se il provisioning dei dispositivi condivisi viene eseguito in una posizione ben definita che può [](/azure/active-directory/conditional-access/location-condition) essere identificata con un intervallo di indirizzi IP, è possibile configurare l'accesso condizionale usando posizioni denominate per questi dispositivi. Questo condizionale consentirà a questi dispositivi di accedere alle risorse aziendali solo quando si trova all'interno della rete.

### <a name="require-compliant-device"></a>Richiedi dispositivo conforme

>[!NOTE]
>La conformità del dispositivo richiede una licenza intune.

Se si registrano dispositivi condivisi in Intune, è possibile configurare la conformità dei dispositivi come controllo in Accesso condizionale in modo che solo i dispositivi conformi possano accedere alle risorse aziendali. Teams dispositivi possono essere configurati per i criteri di accesso condizionale in base alla conformità dei dispositivi. Per altre informazioni, vedere Accesso condizionale: Richiedere dispositivi conformi o [ibridi Azure AD aggiunti al dispositivo.](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)

Per impostare l'impostazione di conformità per i dispositivi con Intune, vedere Usare i criteri di conformità per impostare le regole per i dispositivi [gestiti con Intune.](/intune/protect/device-compliance-get-started)

>[!NOTE]
> I dispositivi condivisi usati per l'hotdesking devono essere esclusi dai criteri di conformità. I criteri di conformità impediscono ai dispositivi di registrarsi nell'account utente dell'hot desk. Usare invece posizioni denominate per proteggere questi dispositivi.
> Per aumentare la sicurezza, è anche possibile [richiedere](/azure/active-directory/authentication/tutorial-enable-azure-mfa) l'autenticazione a più fattori per gli utenti di hot desking oltre ai criteri di posizione denominata.

### <a name="sign-in-frequency"></a>Frequenza di accesso

In Accesso condizionale è possibile configurare la frequenza di accesso [per](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) richiedere agli utenti di eseguire di nuovo l'accesso per accedere a una risorsa dopo un periodo di tempo specificato. Se viene applicata la frequenza di accesso per gli account della chat room, i dispositivi condivisi si disconnettano finché non vengono nuovamente connessi da un amministratore. Microsoft consiglia di escludere i dispositivi condivisi da eventuali criteri di frequenza di accesso.

### <a name="filters-for-devices"></a>Filtri per i dispositivi

[Filtri per i dispositivi](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) è una funzionalità di Accesso condizionale che consente di configurare criteri più granulari per i dispositivi in base alle proprietà dei dispositivi disponibili in Azure AD. È anche possibile usare valori personalizzati impostando gli attributi di estensione da 1 a 15 nell'oggetto dispositivo e quindi usando questi valori.

Usare i filtri per i dispositivi per identificare i dispositivi ad area comune e abilitare i criteri in due scenari chiave:

1.  Esclusione dei dispositivi condivisi dai criteri applicati per i dispositivi personali. Ad esempio, la richiesta di conformità dei dispositivi non viene applicata per i dispositivi condivisi usati per l'hot desking, ma viene applicata per tutti gli altri dispositivi in base al numero di modello.

2.  Applicazione di criteri speciali nei dispositivi condivisi che non devono essere applicati ai dispositivi personali. Ad esempio, se si richiedono percorsi denominati come criteri solo per i dispositivi ad area comune in base a un attributo di estensione impostato per questi dispositivi, ad esempio "CommonAreaPhone".

>[!NOTE] 
> Alcuni attributi, ad esempio **model,** **manufacturer** e **operatingSystemVersion,** possono essere impostati solo quando i dispositivi sono gestiti da Intune. Se i dispositivi non sono gestiti da Intune, usare gli attributi di estensione.
