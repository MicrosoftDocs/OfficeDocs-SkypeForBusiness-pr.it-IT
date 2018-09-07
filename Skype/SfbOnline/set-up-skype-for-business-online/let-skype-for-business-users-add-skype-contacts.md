---
title: Consenti agli utenti di Skype for Business di aggiungere contatti Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: 'See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. '
ms.openlocfilehash: 98701f55bd1cdf2c6a5f8177d05a95030a4a04a5
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850090"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Consenti agli utenti di Skype for Business di aggiungere contatti Skype

[] Con Skype for Business, gli utenti possono cercare e scambiare messaggi istantanei con tutti gli utenti di Skype, l'app gratuita. Questo articolo spiega di cosa hai bisogno perché la tua azienda possa aggiungere contatti Skype. 
  
Per eseguire questa procedura, è necessario avere autorizzazioni di [Informazioni sui ruoli di amministratore di Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365.

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**
  
1. Accedere con l'account di amministrazione di Office 365 in [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. In Interfaccia di amministrazione di Office 365, vai a **Interfacce di amministrazione** > **Skype for Business**. 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. In **Interfaccia di amministrazione di Skype for Business**, scegli **Organizzazione** > **Comunicazioni esterne**. 
    
4. Per impostazione predefinita, gli utenti possono comunicare con tutte le altre persone nel mondo che usano Skype for Business (supponendo che il firewall sia stato configurato per permetterlo). 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Se desideri che i tuoi utenti possano comunicare in chat con gli utenti Skype MA non con altri utenti che usano Skype for Business, nella casella di riepilogo a discesa, scegli **Attiva solo per i domini consentiti**. (Quando consenti agli utenti di contattare utenti Skype, skype.com viene automaticamente aggiunto come dominio consentito dietro le quinte.) 
    
    Se vuoi consentire il contatto da tutte le altre aziende al mondo che usano Skype for Business, tranne alcune specifiche, scegli **Attiva eccetto i domini bloccati**, quindi scegli **+** per aggiungere tali domini. Tutti potranno contattare la tua azienda tranne le persone in quei domini specifici. Alcune aziende possono scegliere questa opzione, ad esempio, in caso di controversia legale, qualora fosse necessario assicurarsi che non ci sia alcun contatto con l'altra azienda.
    
5. Scegli **Consenti l'utilizzo di Skype for Business per comunicare con utenti Skype all'esterno dell'organizzazione**. 
    
6.  Se si utilizza Windows Firewall, Skype for Business apre automaticamente le porte necessarie.
    
    Se la tua organizzazione usa un'altra soluzione per limitare la connessione a Internet dei computer sulla rete, assicurati che i computer client siano in grado di accedere a tutti gli [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per la connettività di Skype e la ricerca directory Skype. A tale scopo, potrebbe essere necessario aggiungerli all'elenco degli elementi consentiti in uscita nella configurazione dell'infrastruttura del firewall o del proxy.
    
7. **ATTENDI FINO A 24 ORE PRIMA DEL TEST**. Ogni volta che modifichi le impostazioni per le comunicazioni esterne, possono occorrere fino a 24 ore perché le modifiche vengano distribuite su tutti i data center.
    
8. Mostra ai tuoi utenti come trovare e aggiungere contatti di Skype ai propri elenchi di contatti Skype for Business. Invitali a consultare l'articolo [Cercare persone in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).
    
## <a name="test-and-troubleshoot"></a>Test e risoluzione dei problemi

Per testare le tue impostazioni, ti servirà un contatto in Skype che non sia dietro il firewall della tua azienda. Può essere connesso a Skype mediante un account Gmail, Outlook.com o altro tipo di account di posta elettronica.
  
1. Dopo aver modificato le impostazioni di comunicazione esterna, **ASPETTA FINO A 24 ORE PER TESTARLE**.
    
2. Esci da Skype for Business e poi accedi di nuovo, in modo da visualizzare la possibilità di cercare nella Directory Skype. 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. In Skype for Business, cerca il tuo contatto Skype e inviagli una richiesta di chat. 
    
    Se viene visualizzato un errore che indica che non è stato possibile inviare il messaggio a causa di criteri aziendali, devi verificare le [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). 
    
4. Un altro metodo per testare se il problema è causato dal firewall è spostarti in un luogo dove la rete WiFi non si trova dietro il firewall, ad esempio in un bar, e utilizzare Skype for Business per inviare una richiesta di chat al tuo contatto Skype. 
    
  - **Se hai inviato una richiesta al tuo contatto Skype e lui non l'ha mai ricevuta**, chiedigli di inviarti una richiesta di chat. Se il problema è stabilire una connessione tra Skype e Skype for Business, in questo modo spesso si risolve.
    
  - Se il messaggio viene consegnato dal bar ma non quando sei al lavoro, allora il problema è senz'altro il tuo firewall. 
    
## <a name="what-you-can-and-cant-do"></a>Funzionalità disponibili e non disponibili

- **Skype for Businessper Mac** non consente di cercare e comunicare con contatti Skype.
    
- Mentre tu puoi cercare e trovare utenti Skype, loro non possono cercare e trovare utenti Skype for Business. Devi inviare loro una richiesta di contatto e loro devono accedere a Skype e accettare la richiesta prima che possiate comunicare con i messaggi istantanei. 
    
- Non è possibile consentire la connettività per la messaggistica istantanea con altri provider come Google o Facebook. Non puoi utilizzare Skype for Business per inviare messaggi di testo da cellulare.

- Quali funzionalità sono disponibili quando aggiungi contatti Skype?
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>I contatti di Skype che hanno effettuato l'accesso con il loro account Microsoft (noto in precedenza come Windows Live ID) possono beneficiare di una parte ma non di tutte le funzioni disponibili quando parlano con un utente Skype for Business.

I contatti Skype che hanno effettuato l'accesso con il loro account Microsoft (noto in precedenza come Windows Live ID) possono beneficiare di una parte ma non di tutte le funzioni disponibili quando parlano con un utente Skype for Business.
  
|**Non disponibile con contatti di Skype**|Conversazioni video|
|:-----|:-----|
| Messaggi istantanei tra due persone <br/>  Presenza <br/>  Conversazioni di messaggistica istantanea tra più utenti <br/> | Conversazioni audio e video con tre o più persone <br/>  Condivisione di desktop e programmi <br/>  Condivisione di desktop e programmi <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Argomenti correlati

[Consentire agli utenti di contattare utenti Skype for Business esterni](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

  
 