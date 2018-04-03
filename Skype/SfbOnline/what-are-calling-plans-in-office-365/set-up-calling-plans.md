---
title: Configurare le chiamate PSTN per Skype for Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 03/30/2018
ms.topic: article
ms.assetid: 57893158-1acd-44ac-acaf-19f58264a9e0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
- LIL_Placement
description: 'Learn how in Office 365 Calling Plan (PSTN Calling plan) to buy and set up licenses, get phone numbers, add and assign emergency locations and phone numbers to users, and tell your users about their new phone numbers. '
ms.openlocfilehash: dcba074f1c0e6966ef0632a95035e681aa25a194
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="set-up-calling-plans"></a>Configurare le chiamate PSTN per Skype for Business

Calls to other Skype for Business users are free, but if you want your users to be able to call phones outside of your business, get a Domestic Calling Plan or an International Calling Plan in Office 365. It's easy to set this up for your business. 

## <a name="step-1-find-out-if-calling-plans-are-available-in-your-countryregion"></a>Passaggio 1: Sapere se la chiamata dei piani sono disponibili nel paese/area geografica

Passare alla [disponibilità paese e alle aree per le conferenze Audio e la chiamata a piani](..//country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e selezionare il paese o l'area per ottenere informazioni sulla disponibilità sui piani di chiamata, nonché informazioni relative a pagamento per conferenze Audio, il sistema telefonico e numero verde i numeri e titoli di coda di comunicazioni.
  
## <a name="step-2-buy-and-assign-licenses"></a>Passaggio 2: Acquistare e assegnare licenze

1. If the Phone System in Office 365 feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses. Dopo avere licenze **Sistema telefonico** , acquistare [La chiamata dei piani di Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md). See [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses and plan. 
    
    > [!TIP]
    > Le licenze Cloud PBX e i piani per chiamate vocali vanno di pari passo, perciò per vedere l'opzione per acquistare un piano di chiamate vocali devi prima comprare le licenze Cloud PBX.
  
2. First assign the licenses, and then assign a Calling Plan to the people in your organization. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
## <a name="step-3-get-phone-numbers"></a>Passaggio 3: Ottenere i numeri di telefono

Esistono tre modi per ottenere nuovi numeri utente:

- **Utilizzare il Skype per l'interfaccia di amministrazione di Business.** Per alcuni paesi, è possibile ottenere numeri per i ponti di audioconferenze con il Skype per interfaccia di amministrazione di Business, vedere [Getting numeri di telefono del servizio](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Porte i numeri esistenti.** Consente di porta o trasferire i numeri esistenti dal provider di servizi corrente o gestore telefonico a Office 365. [Trasferire i numeri di telefono a Office 365](transfer-phone-numbers-to-office-365.md) o [numeri di telefono di gestione dell'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per ulteriori informazioni che consentono di eseguire questa operazione, vedere.  
  
- **Utilizzare un modulo di richiesta per nuovi numeri.** In alcuni casi (a seconda del paese/area geografica) non sarà in grado di ottenere numeri di telefono nuovo utilizzando il Skype per interfaccia di amministrazione di Business o sarà necessario area codici o i numeri di telefono specifico. In questo caso, dovrai scaricare un modulo e inviarcelo. Per ulteriori informazioni, vedere [Manage i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) . 


## <a name="step-4-add-emergency-addresses-and-locations-for-your-organization"></a>Passaggio 4: Aggiungere gli indirizzi di emergenza e percorsi per l'organizzazione
<a name="bkmk_add_addresses"> </a>

Un indirizzo di emergenza deve essere associato a un numero di telefono. Quando si verifica questa associazione può variare in paese e aree. Ad esempio, negli Stati Uniti, è necessario associare un indirizzo di emergenza quando si assegna il numero di telefono per l'utente. Nel Regno Unito, è necessario associare un indirizzo di emergenza per il numero di telefono quando si desidera ottenere i numeri di telefono da Office 365 o il trasferimento di numeri di telefono da provider di servizi corrente. 

Per aggiungere un indirizzo di emergenza per l'organizzazione, in Skype per Business admin center passare a **Voice** > **percorsi Emergency** > **Aggiungi nuovo indirizzo**. Per ulteriori informazioni, vedere [Add o remove e indirizzo di emergenza per l'organizzazione](../what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization.md) .

Per aggiungere un percorso di emergenza per l'organizzazione in Skype per interfaccia di amministrazione di Business, passare a **Voice** > **percorsi Emergency** > **Aggiungi nuovo indirizzo**. Per ulteriori informazioni, vedere [aggiungere, modificare o rimuovere un percorso di emergenza per l'organizzazione](../what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization.md) .

    
## <a name="step-5-assign-an-emergency-address-and-a-phone-number-to-a-user"></a>Passaggio 5: Assegnare un indirizzo di emergenza e un numero di telefono a un utente
<a name="bkmk_add_addresses"> </a>

Quando imposta la chiamata dei piani di Office 365, è necessario assegnare un numero di telefono e l'indirizzo di emergenza per ogni utente. Prima che è possibile associare a un numero di telefono, è necessario creare l'indirizzo di emergenza. 

Per aggiungere un indirizzo di emergenza per un utente, in Skype per interfaccia di amministrazione di Business, passare a **Voice** > **utenti VoIP** > **percorso Emergency** > **assegnare numero** > **Cambia percorso**. Per ulteriori informazioni, vedere [assegnare o modificare un indirizzo di emergenza per un utente](../what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user.md) .

   > [!NOTE]
   > È inoltre possibile assegnare un indirizzo di emergenza quando si assegna un numero di telefono.

Per assegnare un numero di telefono a un utente, in Skype per interfaccia di amministrazione di Business, passare a **Voice** > **utenti VoIP** > **assegnare numero** > **Cambia percorso**. Per ulteriori informazioni, vedere [assegnare, modificare o rimuovere un numero di telefono di un utente](../what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user.md) .

    
## <a name="step-6-tell-your-users-about-their-new-phone-numbers"></a>Passaggio 6: Informare gli utenti ai nuovi numeri di telefono
<a name="bkmk_add_addresses"> </a>

Consigliamo di inviare e-mail o usare il metodo di comunicazione standard dell'azienda per comunicare alle persone il nuovo numero di telefono. 

Ecco come è possibile visualizzare tale numero di telefono nel proprio app **Skype for Business** :
  
1. Esegui l'accesso a Skype for Business sul desktop.
    
2. Seleziona **Impostazioni** > **Strumenti** > **Opzioni**. 
    
     ![To view your phone number, go to Settings > Tools > Options.](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. Poi seleziona **Telefoni**. 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
In **Team Microsoft che**gli utenti possono visualizzare il numero di telefono fare clic sulle **chiamate** nel riquadro di spostamento sinistro. Il numero di telefono viene visualizzato sopra la tastiera.

![Un utente può visualizzare il numero di Microsoft Teams facendo clic sulle chiamate nel riquadro di spostamento sinistro.](../images/teams-phone-number.png)

## <a name="what-else-do-you-need-to-know"></a>Per saperne di più
<a name="bkmk_add_addresses"> </a>

- Spesso per indirizzo per gli interventi di emergenza si può intendere un indirizzo civico, un indirizzo stradale o un indirizzo fisico. Si tratta dell'indirizzo stradale o dell'indirizzo civico di un luogo di lavoro per l'organizzazione.
    
- Solo gli indirizzi per gli interventi di emergenza sono convalidati, non le posizioni.
    
- Se desideri consultare ulteriori informazioni sugli indirizzi di emergenza, vedi [Che cosa sono il routing delle chiamate, gli indirizzi e le posizioni per gli interventi di emergenza?](../what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing.md)
    
## <a name="do-you-want-to-automate-assigning-phone-numbers"></a>Vuoi automatizzare l'assegnazione dei numeri di telefono?
<a name="bkmk_add_addresses"> </a>

Se conosci Windows PowerShell, puoi usare questi cmdlet per automatizzare l'assegnazione dei numeri di telefono ai tuoi utenti. 
  
- [Get-CsOnlineTelephoneNumber](https://technet.microsoft.com/en-us/library/mt243818.aspx): Recupera i numeri di telefono dal tuo elenco vocale aziendale.
    
- [Set-CsOnlineVoiceUser](https://technet.microsoft.com/en-us/library/mt243817.aspx): Imposta i numeri di telefono.
    
Per maggiori informazioni, consulta [Riferimento rapido:Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362776%28v=ocs.15%29.aspx).
  
   > [!NOTE]
   > Se hai bisogno di ulteriori numeri di telefono, visita la pagina [Contattare il supporto per i prodotti aziendali - Guida per gli amministratori](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](transferring-phone-numbers-common-questions.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 