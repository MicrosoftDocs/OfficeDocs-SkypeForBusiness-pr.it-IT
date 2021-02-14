---
title: Consentire agli utenti di Skype for Business di aggiungere contatti Skype
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: "Scopri come consentire alle persone che usano Skype for Business di contattare utenti Skype for Business esterni all'organizzazione e aggiungerli al loro elenco di contatti. "
ms.openlocfilehash: 71282fe105c85cadca9aab341fc1b5e6ffbe47d2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164475"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Consentire agli utenti di Skype for Business di aggiungere contatti Skype

Con Skype for Business, i tuoi utenti possono cercare e messaggi istantanei con chiunque usi Skype, l'app gratuita! Questo articolo spiega di cosa hai bisogno perché possano aggiungere contatti Skype. 
  
Per eseguire questa [operazione, è](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) necessario avere autorizzazioni di amministratore in Microsoft 365 o Office 365.

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**
  
1. Accedi con il tuo account di amministratore di Microsoft 365 o Office 365 all'indirizzo [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) .
    
2. Nell'interfaccia di amministrazione, vai **alle interfaccia di** amministrazione di Skype for  >  **Business.** 
    
    ![Scegliere l'interfaccia di amministrazione di Skype for Business.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Nell'**interfaccia di amministrazione di Skype for Business** scegliere **Organizzazione** > **Comunicazioni esterne**. 
    
4. Per impostazione predefinita, gli utenti possono comunicare con tutte le altre persone nel mondo che usano Skype for Business (presupponendo che il firewall sia stato configurato per consentire questa operazione). 
    
    ![Scegli Consenti alle persone di usare Skype for Business per comunicare con Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Se desideri che i tuoi utenti chattino con gli utenti Skype, ma non con altri utenti che usano Skype for Business, scegli Sì solo per i **domini consentiti.** Quando abiliti il contatto con gli utenti Skype, skype.com viene automaticamente aggiunto come dominio consentito dietro le quinte. 
    
    Se si desidera consentire il contatto da tutte le altre aziende del mondo che utilizzano Skype for Business, tranne quelle specifiche, scegliere Sì tranne i domini bloccati **e** scegliere di aggiungere **+** tali domini. Tutti potranno contattare l'utente tranne le persone di questi domini specifici. Alcune aziende potrebbero scegliere questa opzione, ad esempio in caso di controversia legale e devono verificare che non ci sia alcun contatto con l'altra azienda.
    
5. Scegliere **Consenti alle persone di usare Skype for Business per comunicare con utenti Skype esterni all'organizzazione.** 
    
6.  Se si usa Windows Firewall, Skype for Business apre automaticamente le porte richieste.
    
    Se la tua organizzazione usa un'altra soluzione per limitare la connessione a Internet dei computer sulla rete, assicurati che i computer client siano in grado di accedere a tutti gli indirizzi [IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) e gli URL per la connettività di Skype e la ricerca directory Skype. A questo scopo può essere necessario aggiungerli all'elenco degli elementi consentiti in uscita nella configurazione dell'infrastruttura del firewall o del proxy.
    
7. **ATTENDI FINO A 24 ORE PER IL TEST.** Ogni volta che si modificano le impostazioni per le comunicazioni esterne, possono essere necessarie fino a 24 ore prima che le modifiche possano essere popolate in tutti i data center.
    
8. Mostra agli utenti come trovare e aggiungere contatti Skype al loro elenco di contatti Skype for Business. Indica loro di [cercare persone in Skype for Business.](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19)
    
## <a name="test-and-troubleshoot"></a>Test e risoluzione dei problemi

Per testare la configurazione, devi avere un contatto su Skype che non sia dietro il firewall della tua azienda. Possono accedere a Skype con un account Gmail, un Outlook.com account o un altro tipo di account di posta elettronica.
  
1. Dopo aver modificato le impostazioni per le comunicazioni esterne, **ATTENDI FINO A 24 ORE PER TESTARE.**
    
2. Disconnettersi da Skype for Business e accedere di nuovo in modo da visualizzare l'opzione per cercare nella Directory Skype. 
    
    ![Quando l'opzione Directory Skype è evidenziata, puoi cercare persone che dispongono di account Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. In Skype for Business, cerca il tuo contatto in Skype e invia una richiesta di chat. 
    
    Se ricevi il messaggio che non è stato inviato a causa dei criteri aziendali, devi verificare le impostazioni [del firewall.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) 
    
4. Un altro modo per verificare se il problema è il tuo firewall è accedere a un wi-fi che non si trova dietro il firewall, ad esempio in un bar, e usare Skype for Business per inviare una richiesta di chat al tuo contatto Skype. 
    
   - **Se hai inviato una richiesta al tuo contatto Skype e non** l'ha mai ricevuta, chiedigli di inviarti una richiesta di chat. Se il problema è stabilire una connessione tra Skype e Skype for Business, spesso questo si risolve.
    
   - Ora, se il messaggio viene inviato al bar ma non quando sei al lavoro, allora il problema è il tuo firewall. 
    
## <a name="what-you-can-and-cant-do"></a>Cosa è possibile e non si può fare

- **Skype for Business per Mac** non consente di cercare e comunicare con i contatti Skype.
    
- Quando la ricerca nell'elenco è abilitata, puoi cercare e trovare utenti Skype e Skype for Business. Se per qualche motivo non riesci a trovarli eseguendo una ricerca nell'elenco, puoi inviare loro una richiesta di contatto e poi chiedere loro di accedere a Skype e accettarla, in modo da poter inviare loro un messaggio istantaneo. 
    
- Non è possibile consentire la connettività per la messaggistica istantanea con altri provider come Google o Facebook. Non è possibile usare Skype for Business per inviare SMS da cellulare.

- Non è possibile registrare chiamate audio o video tra un contatto Skype e un contatto Skype for Business.
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>Quali funzionalità sono disponibili quando si aggiungono contatti Skype?

I contatti Skype che hanno effettuato l'accesso con il proprio account Microsoft (in precedenza Windows Live ID) possono ottenere alcune funzionalità, ma non tutte, quando parlano con gli utenti di Skype for Business.
  
|**Disponibile con contatti Skype**|**Non disponibile con i contatti Skype**|
|:-----|:-----|
| Conversazioni video <br/>  Messaggistica istantanea da persona a persona <br/>  Icone di presenza <br/> | Conversazioni istantanee tra più utenti <br/>  Conversazioni audio e video con tre o più persone <br/>  Condivisione di desktop e programmi <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Argomenti correlati

[Consentire agli utenti di contattare utenti Skype for Business esterni](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

  
 
