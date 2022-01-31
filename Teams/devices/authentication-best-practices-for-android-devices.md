---
title: Procedure consigliate per l'autenticazione Microsoft Teams gestione condivisa dei dispositivi Android.
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Procedure consigliate per la gestione di dispositivi Android condivisi in Teams. Sono disponibili l'accesso condizionale, i criteri per le password, i consigli per l'autenticazione a più fattori e altro ancora.
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
ms.openlocfilehash: 070c662c09d8b8159dbce850501026f67dabb203
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279234"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Procedure consigliate per l'autenticazione Teams gestione dei dispositivi condivisi nei dispositivi Android

Gli obiettivi dei dispositivi usati con Teams rendono necessarie diverse strategie di gestione dei dispositivi. Ad esempio, un tablet aziendale personale usato da un singolo venditore ha un set diverso di esigenze rispetto a un telefono di chiamata condiviso da molte persone del servizio clienti.

Gli amministratori della sicurezza e i team delle operazioni devono pianificare i dispositivi che possono essere usati nell'organizzazione. Devono implementare *misure di* sicurezza più adatte a ogni scopo. I suggerimenti di questo articolo semplificano alcune di queste decisioni.

>[!NOTE]
>L'accesso condizionale richiede Azure Active Directory (Azure AD) Premium abbonamento.

>[!NOTE]
>I criteri per i dispositivi mobili Android potrebbero non essere applicabili Teams dispositivi Android.

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>I consigli di autenticazione sono diversi per i dispositivi Android personali e condivisi

I Teams condivisi non possono usare gli stessi requisiti per la registrazione e la conformità usati nei dispositivi personali. L'applicazione dei requisiti di autenticazione dei dispositivi personali ai dispositivi condivisi causerà problemi di accesso.

1.  **I dispositivi vengono disconnessi a causa dei criteri per le password.**

Gli account usati nei Teams hanno un criterio di scadenza password. Gli account usati con i dispositivi condivisi non hanno un utente specifico per aggiornarli e ripristinarli allo stato di funzionamento alla scadenza delle password. Se l'organizzazione richiede la scadenza e la reimpostazione occasionale delle password, questi account smetteranno di funzionare nei dispositivi Teams finché un amministratore di Teams non reimposta la password e non accede di nuovo.

**Sfida**: quando si tratta di accedere. Teams da un dispositivo, l'account di una persona ha un criterio di scadenza password. Quando la password scadrà, verrà semplicemente cambiata. Tuttavia, gli account usati *nei dispositivi condivisi* (account delle risorse) potrebbero non essere connessi a una singola persona che può cambiare una password in base alle esigenze. Ciò significa che una password può scadere e lasciare i dipendenti sul posto, senza sapere come riprendere il lavoro.

Quando l'organizzazione richiede la reimpostazione della password o applica la scadenza della password, assicurarsi che un amministratore di Teams sia pronto a reimpostare la password in modo che questi account condivisi possano accedere di nuovo.

2.  **I dispositivi non riescono ad accedere a causa dei criteri di accesso condizionale.**

**Sfida**: i dispositivi condivisi non sono conformi ai criteri Azure AD di accesso condizionale per gli account utente o i dispositivi personali. Se i dispositivi condivisi sono raggruppati con account utente o dispositivi personali per un criterio di accesso condizionale, l'accesso avrà *esito negativo*.

Ad esempio, se è necessaria l'autenticazione a più fattori per l'accesso Teams, è necessario l'immissione di un codice da parte dell'utente per completare l'autenticazione. I dispositivi condivisi in genere non hanno un singolo utente in grado di configurare e completare l'autenticazione a più fattori. Inoltre, se l'account deve eseguire di nuovo l'autenticazione ogni X giorni, un dispositivo condiviso non può risolvere il problema senza l'intervento di un utente.

L'autenticazione a più fattori non è supportata con i dispositivi condivisi. Di seguito sono descritti i metodi da usare.

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>Procedure consigliate per la distribuzione di dispositivi Android condivisi con Teams

Microsoft consiglia le impostazioni seguenti quando si distribuiscono Teams dispositivi nell'organizzazione.

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**Usare un account risorsa e limitare la scadenza della password**

Teams dispositivi condivisi devono usare una cassetta [postale Exchange delle risorse.](/exchange/recipients-in-exchange-online/manage-resource-mailboxes) La creazione di queste cassette postali genera automaticamente un account. Questi account possono essere sincronizzati con Azure AD da Active Directory o creati direttamente in Azure AD. I criteri di scadenza delle password per gli utenti verranno applicati anche agli account usati nei dispositivi condivisi Teams, quindi, per evitare interruzioni causate dai criteri di scadenza delle password, impostare i criteri di scadenza delle password per i dispositivi condivisi in modo che non scadano mai.

A partire da dispositivi Teams CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams versione 1449/1.0.94.2021022403 per telefoni Teams) e [CY2021 Aggiornamento #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams versione 1449/1.0.96.2021051904 per Microsoft Teams Rooms in Android), gli amministratori del tenant possono accedere ai dispositivi Teams in remoto. Invece di condividere le password con i tecnici per configurare i dispositivi, gli amministratori tenant devono usare l'accesso remoto per emettere codici di verifica. L'accesso può essere eseguito per questi dispositivi dall'Teams di amministrazione.

Per altre informazioni, vedere [Provisioning remoto e accesso per Teams dispositivi Android](/MicrosoftTeams/devices/remote-provision-remote-login). 

### <a name="review-these-conditional-access-policies"></a>**Esaminare questi criteri di accesso condizionale**

Azure AD l'accesso condizionale imposta requisiti aggiuntivi che i dispositivi devono soddisfare per poter accedere. Per Teams, leggere le indicazioni seguenti per determinare se sono stati creati i criteri che consentiranno agli utenti di dispositivi condivisi di eseguire il proprio lavoro.

> [!TIP]
> Per una panoramica dell'accesso condizionale, vedere [Che cos'è l'accesso condizionale](/azure/active-directory/conditional-access/overview)?

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>Non usare l'autenticazione a più fattori per i dispositivi condivisi

Gli account per i dispositivi condivisi sono collegati a una sala o a uno spazio fisico, invece che a un account utente finale. Poiché i dispositivi condivisi non supportano l'autenticazione a più fattori, escludere i dispositivi condivisi dai criteri di autenticazione a più fattori.

>[!TIP]
>Usare una [posizione denominata o](/azure/active-directory/conditional-access/location-condition) [richiedere un dispositivo conforme](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) per proteggere i dispositivi condivisi.

### <a name="you-can-use-location-based-access-with-named-locations"></a>È possibile usare l'accesso in base alla posizione con posizioni denominate

Se il provisioning dei dispositivi condivisi viene eseguito in una posizione ben definita che può essere identificata con un intervallo di indirizzi IP, è possibile configurare l'accesso condizionale usando posizioni denominate per questi dispositivi.[](/azure/active-directory/conditional-access/location-condition) Questo condizionale consentirà a questi dispositivi di accedere alle risorse aziendali solo quando si trova all'interno della rete.

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>Quando e quando non richiedere dispositivi condivisi conformi

>[!NOTE]
>La conformità del dispositivo richiede una licenza intune.

Se si registrano dispositivi condivisi in Intune, è possibile configurare la conformità dei dispositivi come controllo in Accesso condizionale in modo che solo i dispositivi conformi possano accedere alle risorse aziendali. Teams dispositivi possono essere configurati per i criteri di accesso condizionale in base alla conformità dei dispositivi. Per altre informazioni, vedere [Accesso condizionale: Richiedere un dispositivo Azure AD conforme o ibrido](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device).

Per impostare l'impostazione di conformità per i dispositivi con Intune, vedere Usare i criteri di conformità per impostare le regole per [i dispositivi gestiti con Intune](/intune/protect/device-compliance-get-started).

>[!NOTE]
> I dispositivi condivisi usati per *l'hot desking* devono essere esclusi dai criteri di conformità. I criteri di conformità impediscono ai dispositivi di registrarsi nell'account utente dell'hot desk. **Usare invece posizioni denominate per proteggere questi dispositivi**.
> Per aumentare la sicurezza, è anche [possibile richiedere](/azure/active-directory/authentication/tutorial-enable-azure-mfa) l'autenticazione a più fattori per gli utenti e gli account utente di *hot desking* oltre ai criteri di posizione denominati.

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>Escludere i dispositivi condivisi dalle condizioni di frequenza di accesso

In Accesso condizionale è possibile configurare la frequenza [di accesso per](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) richiedere agli utenti di eseguire di nuovo l'accesso per accedere a una risorsa dopo un periodo di tempo specificato. Se viene applicata la frequenza di accesso per gli account della chat room, i dispositivi condivisi si disconnettano finché non vengono nuovamente connessi da un amministratore. Microsoft consiglia di escludere i dispositivi condivisi da eventuali criteri di frequenza di accesso.

### <a name="using-filters-for-devices"></a>Uso dei filtri per i dispositivi

[Filtri per dispositivi](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) è una funzionalità di Accesso condizionale che consente di configurare criteri più granulari per i dispositivi in base alle proprietà dei dispositivi disponibili in Azure AD. È anche possibile usare valori personalizzati impostando gli attributi di estensione da 1 a 15 nell'oggetto dispositivo e quindi usando questi valori.

Usare i filtri per i dispositivi per identificare i dispositivi ad area comune e abilitare i criteri in due scenari chiave:

1.  Esclusione dei dispositivi condivisi dai criteri applicati per i dispositivi personali. Ad esempio, la richiesta di conformità dei dispositivi non viene applicata per i dispositivi condivisi usati per *l'hot* desking, ma viene applicata per tutti gli altri dispositivi, in base al numero di modello.

2.  Applicazione di criteri speciali nei dispositivi condivisi *che non devono* essere applicati ai dispositivi personali. Ad esempio, se si richiedono percorsi denominati come criteri solo per i dispositivi ad area comune in base a un attributo di estensione impostato per questi dispositivi, ad esempio "CommonAreaPhone".

>[!NOTE] 
> Alcuni attributi, ad esempio **modello**, **produttore** e **operatingSystemVersion** , possono essere impostati solo quando i dispositivi sono gestiti da Intune. Se i dispositivi non sono gestiti da Intune, usare gli attributi di estensione.