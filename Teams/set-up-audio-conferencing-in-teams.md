---
title: Configurare servizi di audioconferenza per Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: "Informazioni sulla configurazione del servizio di conferenza telefonica con accesso esterno o del servizio Audioconferenza per gli utenti dell'organizzazione che devono usare il telefono per partecipare alle conferenze telefoniche. "
ms.openlocfilehash: d630f6f149f61609209cc4ead23ed7232647cb08
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "37925367"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Configurare servizi di audioconferenza per Microsoft Teams

A volte le persone all’interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione. Microsoft teams include la funzionalità di conferenza audio per questa situazione. Gli utenti possono chiamare riunioni di teams usando un telefono, invece di usare l'app teams in un dispositivo mobile o un PC. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Per le domande frequenti sui servizi di audioconferenza, vedere [Domande frequenti su Audioconferenze](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Passo 1: Verificare se l'Audioconferenza è disponibile nel tuo Paese o nella tua area geografica
<a name="__top"> </a>

Vai a [Disponibilità di audioconferenza e Piani di chiamata per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e seleziona il Paese o l'area geografica per ottenere informazioni sulla disponibilità del servizio di Audioconferenza, nonché informazioni relative a Sistema telefonico, Piani di chiamata, numeri a pagamento e numeri verdi, e Credito per la comunicazione. 
 
## <a name="step-2-get-and-assign-licenses"></a>Passo 2: Ottenere e assegnare licenze
 
1. Per l'Audioconferenza, è necessaria una licenza per ogni utente che configurerà le riunioni con accesso esterno. Per informazioni sulle licenze che è necessario acquistare per i servizi di audioconferenza e sul costo, vedere licenze per i [componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > Il servizio Audioconferenza è incluso nelle licenze Office 365 Enterprise E5 e come componente aggiuntivo.
        
2. Dopo aver acquistato le licenze per Audioconferenza, è necessario assegnarle agli utenti dell'organizzazione che intendono pianificare o coordinare riunioni. Vedere [assegnare licenze agli utenti in Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) acquistati alle persone dell'organizzazione che hanno intenzione di pianificare o condurre riunioni.
    
3. È inoltre consigliabile assegnare licenze di Credito per la comunicazione (non costano nulla) agli stessi utenti a cui sono state assegnate le licenze nel passo precedente. Per altre informazioni sulla configurazione di Credito per la comunicazione, vedere [Configurare Credito per la comunicazione per l'organizzazione](set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> È inoltre possibile configurare il servizio [Audioconferenza con tariffa al minuto](audio-conferencing-pay-per-minute.md).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Passo 3: Ottenere i numeri di servizio per i ponti per audioconferenza
<a name="__top"> </a>

Non è possibile utilizzare numeri di telefono per gli utenti per l'Audioconferenza. È necessario ottenere numeri di servizio. Per i ponti per audioconferenza è possibile ottenere numeri di servizio a pagamento o numeri verdi. Esistono tre modi per ottenere numeri di servizio a pagamento o numeri verdi: 
  
- **Usare l'interfaccia di amministrazione di Microsoft teams**. Per alcuni paesi/aree geografiche è possibile ottenere i numeri di servizio per i ponti di conferenza usando l'interfaccia di amministrazione di Microsoft teams. Vedere [Recupero dei numeri di telefono del servizio](/microsoftteams/getting-service-phone-numbers).
    
- **Trasferire i numeri del servizio esistenti**. È possibile trasferire i numeri di telefono esistenti o eseguirne la portabilità dal provider di servizi o dall'operatore telefonico corrente Office 365. Per ulteriori informazioni, vedere [trasferire i numeri di telefono in team](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) .  
  
- **Usare un modulo di richiesta per nuovi numeri**. A volte, a seconda del paese o dell'area geografica, non sarà possibile ottenere i nuovi numeri di servizio usando l'interfaccia di amministrazione di Microsoft teams oppure saranno necessari numeri di telefono o codici di area specifici. In questo caso è necessario scaricare un modulo di richiesta, compilarlo e inviarlo a Microsoft. Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Passo 4: Assegnare un numero di servizio al ponte per audioconferenza
<a name="__top"> </a>

Dopo aver ottenuto i numeri a pagamento e i numeri verdi per il bridge di conferenza, è necessario assegnarli per consentirne l'uso negli inviti alle riunioni.  

Seguire questa procedura per assegnare un nuovo numero di telefono al Bridge di audioconferenza.

![Icona che mostra il logo di Skype for Business](media/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business:**

 1. Passare all'**interfaccia di amministrazione di Microsoft 365** > **Interfacce di amministrazione** > **Teams** > **Portale legacy**.
 2. Selezionare **Vocale** > **Numeri telefonici**.
 3. Selezionare il numero di telefono e fare clic su **Assegna**.

Per altre informazioni, vedere [modificare i numeri di telefono nel Bridge di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Passo 5: Impostare le lingue predefinite e alternative per un ponte per audioconferenza
<a name="__top"></a> Si desidera quindi impostare le [lingue per gli operatori automatici per i servizi di audioconferenza in Microsoft teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) che l'operatore automatico di conferenza USA per salutare i chiamanti quando effettuano la chiamata a un numero di telefono per i servizi di audioconferenza. 

![Icona che mostra il logo di Skype for Business](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**:

1. Nella dashboard passare a **Riunioni** > **Bridge di conferenza**.
2. Selezionare il numero di telefono del bridge di conferenza, fare clic su **Modifica** e quindi fare clic sulla lingua predefinita.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Passo 6: Configurare le impostazioni del ponte per audioconferenza
<a name="__top"> </a>
    
Dopo aver impostato il ponte per audioconferenza, verifica che le impostazioni predefinite, ad esempio le notifiche di ingresso e di uscita e la lunghezza del PIN siano quelle desiderate; se non lo sono, è possibile modificarle. 

![Icona che mostra il logo di Skype for Business](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**:

1. Nella dashboard passare a **Riunioni** > **Bridge di conferenza**.
2. Selezionare **Impostazioni del bridge**. Verrà visualizzato il riquadro **Impostazioni ponte**. 

Per ulteriori informazioni, consulta [Modificare le impostazioni per un ponte per Audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Passo 7: Assegnare i numeri di telefono con accesso esterno per gli utenti che conducono le riunioni

Dopo aver creato un ponte per Audioconferenza, è necessario impostare i numeri a pagamento e i numeri verdi per gli utenti.

È necessario eseguire questa operazione per tutti gli utenti dell'organizzazione che conducono o pianificano riunioni. 

![Icona che mostra il logo di Skype for Business](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**:

1. Nella dashboard fare clic su **Utenti**, selezionare l'utente nell'elenco e quindi **Modifica**.
2. Selezionare **Modifica** accanto ad **Audioconferenza** e quindi nel riquadro **Audioconferenza** scegliere un numero negli elenchi **Numero a pagamento** e **Numero verde**.

Per ulteriori informazioni, consulta [Assegnare Microsoft come provider di servizi di audioconferenza](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Passo 8: Configurare gli inviti alla riunione (facoltativo)
<a name="__top"> </a>
 
I numeri telefonici di accesso esterno impostati per l'utente verranno aggiunti automaticamente agli inviti alle riunioni inviati ai partecipanti. Se però si preferisce, è possibile aggiungere una guida e collegamenti alle note legali, un messaggio di testo e un piccolo logo aziendale personalizzato. Vedere [Personalizzare gli inviti alle riunioni](meeting-settings-in-teams.md#customize-meeting-invitations).
   
## <a name="related-topics"></a>Argomenti correlati

[Domande frequenti sul servizio di audioconferenza](audio-conferencing-common-questions.md)
  
[Numeri di telefono per i servizi di audioconferenza in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)
  
[Impostare le opzioni per riunioni online e conferenze telefoniche](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
