---
title: Configurare le chiamate PSTN per Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 57893158-1acd-44ac-acaf-19f58264a9e0
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- LIL_Placement
- seo-marvel-mar2020
description: Scopri come configurare Piani per chiamate, inclusi i piani di visualizzazione disponibili nella tua area geografica, acquistare & assegnare licenze, ottenere numeri di telefono e aggiungere indirizzi di emergenza & località.
ms.openlocfilehash: b7593155711597ae94d2db97573c6b6ba7afcc18
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725725"
---
# <a name="set-up-calling-plans"></a>Configurare le chiamate PSTN per Skype for Business

Le chiamate ad altri utenti Teams sono gratuite, ma se si vuole che gli utenti siano in grado di chiamare telefoni al di fuori dell'azienda, ottenere un piano per chiamate nazionali o un piano per chiamate internazionali in Microsoft 365 o Office 365. È facile configurare Piani per chiamate per la tua azienda.  Per altre informazioni sui Piani per chiamate, vedere [Quale piano di chiamata è più giusto per te?](calling-plan-landing-page.md).

## <a name="step-1-find-out-if-calling-plans-are-available-in-your-countryregion"></a>Passaggio 1: Scopri se i Piani per chiamate sono disponibili nel tuo paese/area geografica
Vai a Disponibilità per paese e area geografica per [i](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) piani per audioconferenze e chiamate e seleziona il tuo paese o area geografica per ottenere informazioni sulla disponibilità sui Piani per le chiamate, oltre a informazioni su audioconferenza, Sistema telefonico, numeri a pagamento e a pagamento e crediti per le comunicazioni.

Se i Piani per chiamate non sono disponibili per il paese o l'area geografica, è consigliabile usare Il routing diretto per connettere l'infrastruttura di telefonia locale a Sistema telefonico.  Per altre informazioni, vedere Sistema telefonico [Routing diretto](direct-routing-landing-page.md).
  
## <a name="step-2-buy-and-assign-licenses"></a>Passaggio 2: Acquistare e assegnare licenze
1. Se la Sistema telefonico non è inclusa nel piano Microsoft 365 o Office 365, potrebbe essere necessario acquistare Sistema telefonico **licenze** per i componenti aggiuntivi. Dopo aver acquistato **Sistema telefonico** licenze, acquistare Piani per chiamate per Microsoft 365 [o Office 365](calling-plans-for-office-365.md). Vedere [Microsoft Teams licenze per i componenti aggiuntivi](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)e acquistare le licenze e il piano. 
    
    > [!TIP]
    > **Sistema telefonico** licenze e piani per chiamate in Microsoft 365 o Office 365 vanno insieme, quindi per vedere l'opzione per acquistare Piani per chiamate, è necessario prima avere le licenze Sistema telefonico **chiamate.**
  
2. First assign the licenses, and then assign a Calling Plan to the people in your organization. Vedere [Assegnare Microsoft Teams licenze per i componenti aggiuntivi.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
## <a name="step-3-get-phone-numbers"></a>Passaggio 3: Ottenere i numeri di telefono
Esistono tre modi per ottenere nuovi numeri utente:

- **Usare l'Teams di amministrazione.** Per alcuni paesi/aree geografiche, è possibile ottenere i numeri per gli utenti usando l'interfaccia di amministrazione di Teams, vedere Ottenere numeri di [telefono per gli utenti.](getting-phone-numbers-for-your-users.md)
    
- **Importa i tuoi numeri esistenti.** È possibile trasferire o trasferire i numeri esistenti dal provider di servizi o dal gestore telefonico corrente Microsoft 365 o Office 365. Per altre informazioni, vedere [Trasferire i numeri di telefono Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o Gestire i numeri di telefono per [l'organizzazione.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
  
- **Utilizzare un modulo di richiesta per nuovi numeri.** A volte (a seconda del paese/area geografica) non è possibile ottenere i nuovi numeri di telefono usando l'interfaccia di amministrazione di Teams oppure sono necessari numeri di telefono o codici di area specifici. In questo caso è necessario scaricare un modulo di richiesta, compilarlo e inviarlo a Microsoft. Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 

## <a name="step-4-add-emergency-addresses-and-locations-for-your-organization"></a>Passaggio 4: Aggiungere indirizzi e posizioni per gli interventi di emergenza per l'organizzazione
<a name="bkmk_add_addresses"></a> Un indirizzo di emergenza deve essere associato a un numero di telefono. Quando questa associazione si verifica può variare a seconda del paese e delle aree geografiche. Ad esempio, negli Stati Uniti, è necessario associare un indirizzo di emergenza quando si assegna il numero di telefono per l'utente. Nel Regno Unito è necessario associare un indirizzo di emergenza al numero di telefono quando si riceve il numero di telefono da Microsoft 365 o Office 365 o quando si trasferiscono numeri di telefono dal provider di servizi corrente. 

Per informazioni sulle chiamate di emergenza e sulla gestione degli indirizzi di emergenza, [vedere](what-are-emergency-locations-addresses-and-call-routing.md) Gestire le chiamate di emergenza e Aggiungere, modificare o rimuovere una posizione di emergenza [per l'organizzazione.](add-change-remove-emergency-location-organization.md)
    
## <a name="step-5-assign-an-emergency-address-and-a-phone-number-to-a-user"></a>Passaggio 5: Assegnare un indirizzo di emergenza e un numero di telefono a un utente
<a name="bkmk_add_addresses"></a> Quando si configuraNo piani di chiamata in Office 365, è necessario assegnare un numero di telefono e un indirizzo di emergenza a ogni utente. Prima di poter associare a un numero di telefono, è necessario creare l'indirizzo di emergenza.  Per altre informazioni, vedere [Assegnare o modificare un indirizzo per gli interventi di emergenza.](assign-change-emergency-location-user.md)


> [!TIP]
> Se aggiungi altre persone alla tua azienda appena prima di questo passaggio, possono passare **diverse ore** prima che compaiano nella pagina **Utenti vocali**. C'è un periodo di latenza.



## <a name="step-6-tell-your-users-about-their-new-phone-numbers"></a>Passaggio 6: Indicare agli utenti i nuovi numeri di telefono

Microsoft consiglia di inviare posta elettronica o di usare il metodo di comunicazione preferito dell'azienda per comunicare alle persone i nuovi numeri di telefono.
 
In **Microsoft Teams** gli utenti possono visualizzare il loro numero di telefono facendo clic su **Chiamate** nel riquadro di spostamento sinistro. Il numero di telefono viene visualizzato sopra la tastiera.

![Schermata delle opzioni disponibili dopo aver fatto clic su Chiamate.](media/teams-phone-number.png)


## <a name="do-you-want-to-automate-assigning-phone-numbers"></a>Vuoi automatizzare l'assegnazione dei numeri di telefono?
<a name="bkmk_add_addresses"> </a>

Se conosci Windows PowerShell, puoi usare questi cmdlet per automatizzare l'assegnazione dei numeri di telefono ai tuoi utenti. 
  
- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber?view=skype-ps): Recupera i numeri di telefono dal tuo elenco vocale aziendale.
    
- [Set-CsOnlineVoiceUser](/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps): Imposta i numeri di telefono.
    
Per altre informazioni, vedere Teams [panoramica di PowerShell.](teams-powershell-overview.md)
  

## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](./phone-number-calling-plans/port-order-overview.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md) 

[Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)

[Teams: etichetta di esclusione di responsabilità per chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
