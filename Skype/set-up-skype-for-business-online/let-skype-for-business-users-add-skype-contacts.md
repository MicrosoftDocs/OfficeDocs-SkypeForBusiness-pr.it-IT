---
title: Consentire Skype per gli utenti aziendali di aggiungere contatti Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: 'Vedere come consentire agli utenti che utilizzano Skype per contatto commerciale Skype per gli utenti aziendali di all''esterno dell''organizzazione e aggiungerli all''elenco dei contatti. '
ms.openlocfilehash: 1add1f6e907613d1ac536c92b57cfce7f3cdaf66
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Consentire Skype per gli utenti aziendali di aggiungere contatti Skype

Con Skype per le aziende, gli utenti possono cercare e messaggistica immediata con tutti gli utenti Skype, gratuitamente l'app! In questo articolo viene illustrato che cosa è necessario eseguire in modo che è possibile aggiungere contatti Skype. 
  
In Office 365 a tale scopo, è necessario disporre [delle autorizzazioni di amministratore](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) .
  
1. Accedere con l'account di amministrazione di Office 365 in [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. Nell'interfaccia di amministrazione di Office 365 andare a **Admin Center** > **Skype per le aziende**. 
    
    ![Scegliere Skype per interfaccia di amministrazione di Business.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. **Skype per interfaccia di amministrazione di Business**, selezionare **organizzazione** > **comunicazioni esterne**. 
    
4. Per impostazione predefinita, gli utenti possono comunicare con tutti gli altri utenti in tutto il mondo Skype per le aziende (presupponendo che il firewall è stato configurato per consentire questa operazione). 
    
    ![Selezionare Consenti Skype per le aziende utilizzato dagli utenti per comunicare con Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Se si desidera che gli utenti in chat con gli utenti Skype, ma non si desidera loro di parlare con altri utenti che utilizzano Skype per le aziende, fare clic **su solo per domini consentiti**. Quando si abilita contatto con gli utenti Skype, skype.com viene aggiunto automaticamente come un dominio consentito in background. 
    
    Se si desidera consentire contatto da tutte le altre aziende in tutto il mondo utilizzo Skype for Business, ad eccezione di quelle specifiche, scegliere **su ad eccezione dei domini bloccati**e fare clic su **+** per aggiungere tali domini. Tutti gli utenti saranno in grado di contattare l'utente, ad eccezione di persone in tali domini specifici. (Alcune aziende possono scegliere questa opzione, ad esempio, se sono in controversie legali ed è necessario verificare che non esiste alcun contatto con altri business).
    
5. Scegliere **gli utenti utilizzano Skype per le aziende di comunicare con utenti Skype all'esterno dell'organizzazione**. 
    
6.  Se si utilizza Windows Firewall, Skype per le aziende apre le porte necessarie automaticamente.
    
    Se l'organizzazione utilizza un'altra soluzione per limitare i computer della rete di connettersi a Internet, verificare che i computer client siano in grado di accedere a tutti i [gli indirizzi IP e URL](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per la connettività Skype e ricerca nella Directory Skype. Può essere necessario aggiungerli a in uscita elenco Consenti nella configurazione dell'infrastruttura di firewall o proxy.
    
7. **ATTENDERE fino a 24 ore da TESTARE**. Ogni volta che si modificano le impostazioni di comunicazioni esterne, può richiedere fino a 24 ore per le modifiche da popolare in tutti i data center.
    
8. Mostra agli utenti come trovare e aggiungere Skype contatti al proprio elenco di Skype per i contatti aziendali. Puntino a [ricerca per i partecipanti Skype per le aziende](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).
    
## <a name="test-and-troubleshoot"></a>Risoluzione dei problemi

Per testare l'installazione, è necessario disporre di un contatto in Skype che non sono protetti dal firewall aziendale. È possibile eseguire l'accesso a Skype utilizzando un account Gmail, Outlook.com account o un altro tipo di account di posta elettronica.
  
1. Dopo aver modificare le impostazioni di comunicazioni esterne, **ATTENDERE fino a 24 ore a TEST**.
    
2. Disconnettersi da Skype per le aziende e quindi effettuare nuovamente l'accesso in modo che viene visualizzata l'opzione di eseguire ricerche nella Skype Directory. 
    
    ![Quando viene evidenziato Skype Directory, è possibile cercare persone che dispongono di account Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. In Skype per le aziende, cercare il contatto in Skype e inviare una richiesta a chat. 
    
    Se viene visualizzato il messaggio che non è stato inviato a causa di politica aziendale, è necessario controllare le [impostazioni del firewall](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). 
    
4. Un altro modo per verificare se il problema è il firewall sia passare a una posizione wifi non protetti dal firewall, ad esempio un Internet café e utilizzare Skype for Business per inviare una richiesta per il Skype rivolgersi alla chat. 
    
  - **Se è stata inviata dal contatto Skype una richiesta e che non ricevuti**, chiedere di inviare una richiesta a chat. Se il problema è stato stabilire una connessione tra Skype e Skype per le aziende, che spesso consente di risolvere lo.
    
  - Se il messaggio attraversa in bar, ma non quando si è in ufficio, si conosce il problema è ora del firewall. 
    
## <a name="what-you-can-and-cant-do"></a>Che cosa è possibile e non consentite

- **Skype per le aziende in Mac** non hanno la possibilità di cercare e comunicare con contatti Skype.
    
- Mentre è possibile cercare e trovare gli utenti Skype, è possibile cercare e trovare Skype per gli utenti aziendali. È necessario inviare loro una richiesta di contatto e dispongono di accesso a Skype e accettare, prima che sia possibile messaggistica Istantanea con loro. 
    
- Non è possibile consentire di connettività per messaggistica immediata con altri provider di messaggistica immediata, ad esempio Google o Facebook. È possibile utilizzare Skype per le aziende a inviare messaggi di testo di un telefono cellulare.
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>Le funzionalità sono disponibili quando si aggiungono contatti Skype?

Contatti Skype che ha effettuato l'accesso con l'account Microsoft (precedenza account Windows Live ID) è possono ottenere alcuni, ma non tutti, funzionalità trattano con i Skype per gli utenti aziendali.
  
|**Disponibile con i contatti Skype**|**Non disponibile con i contatti Skype**|
|:-----|:-----|
| Conversazioni video <br/>  Messaggistica immediata tra due persone <br/>  Presenza <br/> | Conversazioni di messaggistica Istantanea con più partecipanti <br/>  Conversazioni audio e video con tre o più persone <br/>  Condivisione desktop e programmi <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Argomenti correlati

[Consentire agli utenti di contattare utenti Skype for Business esterni](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurare Skype for Business online](set-up-skype-for-business-online.md)
