---
title: Procedure consigliate di autenticazione per Microsoft Teams gestione di dispositivi condivisi di dispositivi Android.
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Procedure consigliate per la gestione di dispositivi Android condivisi in Teams. Sono disponibili accesso condizionale, criteri per le password, consigli per l'autenticazione a più fattori e altro ancora.
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
ms.openlocfilehash: 6eef76052f662b26f946bf80839a62186c287b68
ms.sourcegitcommit: d425748a50964ebc78e5d38fce564a444a449f43
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2022
ms.locfileid: "65635464"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Procedure consigliate di autenticazione per Teams gestione di dispositivi condivisi nei dispositivi Android

Gli obiettivi dei dispositivi utilizzati con Teams rendere necessarie diverse strategie di gestione dei dispositivi. Ad esempio, un tablet aziendale personale usato da un singolo venditore ha un set di esigenze diverso da un telefono in chiamata condiviso da molti addetti al servizio clienti.

Gli amministratori della sicurezza e i team operativi devono pianificare i dispositivi che possono essere usati nell'organizzazione. Devono implementare le misure di *sicurezza* più adatte a ogni scopo. Le raccomandazioni di questo articolo semplificano alcune di queste decisioni.

>[!NOTE]
>L'accesso condizionale richiede una sottoscrizione Premium Azure Active Directory (Azure AD).

>[!NOTE]
>I criteri per Android dispositivi mobili potrebbero non essere applicabili ai dispositivi Teams Android.

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>I suggerimenti per l'autenticazione sono diversi per i dispositivi Android personali e condivisi

I dispositivi Teams condivisi non possono usare gli stessi requisiti per la registrazione e la conformità usati nei dispositivi personali. L'applicazione dei requisiti di autenticazione del dispositivo personale ai dispositivi condivisi causerà problemi di accesso.

1.  **I dispositivi vengono disconnessi a causa dei criteri per le password.**

Gli account usati nei dispositivi Teams hanno criteri di scadenza delle password. Gli account usati con i dispositivi condivisi non hanno un utente specifico per aggiornarli e ripristinarli a uno stato funzionante alla scadenza delle password. Se l'organizzazione richiede la scadenza e la reimpostazione occasionale delle password, questi account smetteranno di funzionare nei dispositivi Teams finché un amministratore di Teams non reimposta la password e non esegue di nuovo l'accesso.

**Sfida**: quando si tratta di accedere. Teams da un dispositivo, l'account di una persona ha criteri di scadenza della password. Quando la password scadrà, verrà semplicemente modificata. Tuttavia, gli account usati nei *dispositivi condivisi* (account delle risorse) potrebbero non essere connessi a una sola persona che può cambiare una password in base alle esigenze. Ciò significa che una password può scadere e lasciare i lavoratori sul posto, senza sapere come riprendere il lavoro.

Quando l'organizzazione richiede la reimpostazione della password o applica la scadenza della password, assicurarsi che un amministratore di Teams sia pronto a reimpostare la password in modo che questi account condivisi possano accedere di nuovo.

2.  **I dispositivi non riescono ad accedere a causa dei criteri di accesso condizionale.**

**Sfida**: I dispositivi condivisi non possono essere conformi ai criteri di accesso condizionale di Azure AD per gli account utente o i dispositivi personali. Se i dispositivi condivisi sono raggruppati con account utente o dispositivi personali per un criterio di accesso condizionale, l'accesso *non riesce*.

Ad esempio, se per accedere a Teams è necessaria l'autenticazione a più fattori, è necessario immettere un codice per completare l'autenticazione. I dispositivi condivisi in genere non hanno un singolo utente in grado di configurare e completare l'autenticazione a più fattori. Inoltre, se l'account deve ripetere l'autenticazione ogni X giorni, un dispositivo condiviso non può risolvere il problema senza l'intervento di un utente.

L'autenticazione a più fattori non è supportata con i dispositivi condivisi. I metodi da usare sono descritti di seguito.

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>Procedure consigliate per la distribuzione di dispositivi Android condivisi con Teams

Microsoft consiglia le impostazioni seguenti quando distribuiscono Teams dispositivi nell'organizzazione.

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**Usare un account di risorsa e limitarne la scadenza della password**

Teams dispositivi condivisi devono usare una [cassetta postale delle risorse Exchange](/exchange/recipients-in-exchange-online/manage-resource-mailboxes). La creazione di queste cassette postali genera automaticamente un account. Questi account possono essere sincronizzati con Azure AD da Active Directory o creati direttamente in Azure AD. Eventuali criteri di scadenza delle password per gli utenti verranno applicati anche agli account usati in Teams dispositivi condivisi, pertanto, per evitare interruzioni causate da criteri di scadenza delle password, impostare i criteri di scadenza delle password affinché i dispositivi condivisi non scada mai.

A partire da Teams dispositivi CY21 [Aggiornamento 1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams versione 1449/1.0.94.2021022403 per telefoni Teams) e [CY2 Aggiornamento 2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams versione 1449/1.0.96.2021051904 per Microsoft Teams Rooms in Android), gli amministratori del tenant possono accedere Teams dispositivi in remoto. Invece di condividere le password con i tecnici per configurare i dispositivi, gli amministratori del tenant devono usare l'accesso remoto per emettere codici di verifica. L'accesso può essere eseguito per questi dispositivi dall'interfaccia di amministrazione di Teams.

Per ulteriori informazioni, vedi [Provisioning remoto e accesso per Teams Android dispositivi](/MicrosoftTeams/devices/remote-provision-remote-login). 

### <a name="review-these-conditional-access-policies"></a>**Esaminare questi criteri di accesso condizionale**

L'accesso condizionale di Azure AD imposta requisiti aggiuntivi che i dispositivi devono soddisfare per eseguire l'accesso. Per Teams dispositivi, consultare le indicazioni seguenti per determinare se sono stati modificati i criteri che consentiranno agli utenti di dispositivi condivisi di svolgere il proprio lavoro.

> [!TIP]
> Per una panoramica dell'accesso condizionale, vedere [Che cos'è l'accesso condizionale](/azure/active-directory/conditional-access/overview)?

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>Non usare l'autenticazione a più fattori per i dispositivi condivisi

Gli account per i dispositivi condivisi sono collegati a una chat room o a uno spazio fisico, invece che a un account utente finale. Poiché i dispositivi condivisi non supportano l'autenticazione a più fattori, escludere i dispositivi condivisi da eventuali criteri di autenticazione a più fattori.

>[!TIP]
>Usare una [posizione denominata](/azure/active-directory/conditional-access/location-condition) o [richiedere un dispositivo conforme](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) per proteggere i dispositivi condivisi.

### <a name="you-can-use-location-based-access-with-named-locations"></a>È possibile usare l'accesso basato sulla posizione con posizioni denominate

Se il provisioning dei dispositivi condivisi viene eseguito in una posizione ben definita che può essere identificata con un intervallo di indirizzi IP, è possibile configurare l'accesso condizionale usando [percorsi denominati](/azure/active-directory/conditional-access/location-condition) per questi dispositivi. Questa impostazione condizionale consentirà a questi dispositivi di accedere alle risorse aziendali solo quando si trovano all'interno della rete.

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>Quando e quando richiedere dispositivi condivisi conformi

>[!NOTE]
>La conformità del dispositivo richiede una licenza di Intune.

Se si stanno registrando dispositivi condivisi in Intune, è possibile configurare la conformità dei dispositivi come controllo in Accesso condizionale in modo che solo i dispositivi conformi possano accedere alle risorse aziendali. Teams dispositivi possono essere configurati per i criteri di accesso condizionale in base alla conformità dei dispositivi. Per altre informazioni, vedere [Accesso condizionale: richiedere un dispositivo aggiunto ad Azure AD conforme o ibrido](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device).

Per impostare l'impostazione di conformità per i dispositivi usando Intune, vedere [Usare i criteri di conformità per impostare le regole per i dispositivi gestiti con Intune](/intune/protect/device-compliance-get-started).

>[!NOTE]
> I dispositivi condivisi usati per *l'hot desking* devono essere esclusi dai criteri di conformità. I criteri di conformità impediscono la registrazione dei dispositivi nell'account utente hot desk. **Usa invece posizioni denominate per proteggere questi dispositivi**.
> Per aumentare la sicurezza, è anche possibile [richiedere l'autenticazione a più fattori](/azure/active-directory/authentication/tutorial-enable-azure-mfa) per *gli utenti e gli account utente hot desking* oltre ai criteri di posizione denominati.

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>Escludere i dispositivi condivisi dalle condizioni di frequenza di accesso

In Accesso condizionale è possibile [configurare la frequenza di accesso in](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) modo che richieda agli utenti di accedere di nuovo per accedere a una risorsa dopo un periodo di tempo specificato. Se per gli account delle chat room viene applicata la frequenza di accesso, i dispositivi condivisi verranno disconnessi finché non eseguono di nuovo l'accesso da parte di un amministratore. Microsoft consiglia di escludere i dispositivi condivisi da eventuali criteri di frequenza di accesso.

### <a name="using-filters-for-devices"></a>Uso dei filtri per i dispositivi

[I filtri per i dispositivi](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) sono una funzionalità dell'accesso condizionale che consente di configurare criteri più granulari per i dispositivi in base alle proprietà dei dispositivi disponibili in Azure AD. È anche possibile usare i propri valori personalizzati impostando gli attributi di estensione da 1 a 15 sull'oggetto dispositivo e quindi usando tali attributi.

Usare i filtri per i dispositivi per identificare i dispositivi dell'area comune e abilitare i criteri in due scenari chiave:

1.  Esclusione di dispositivi condivisi dai criteri applicati per i dispositivi personali. Ad esempio, la richiesta di conformità *del dispositivo non viene applicata* per i dispositivi condivisi usati per l'hot desking, ma *viene applicata* a tutti gli altri dispositivi, in base al numero di modello.

2.  Applicazione di criteri speciali sui dispositivi condivisi che *non devono* essere applicati ai dispositivi personali. Ad esempio, la richiesta di posizioni denominate come criterio solo per i dispositivi dell'area comune in base a un attributo di estensione impostato per questi dispositivi (ad esempio: "CommonAreaPhone").

>[!NOTE] 
> Alcuni attributi, ad esempio **modello**, **produttore** e **operatingSystemVersion**, possono essere impostati solo quando i dispositivi vengono gestiti da Intune. Se i dispositivi non sono gestiti da Intune, usa gli attributi di estensione.
