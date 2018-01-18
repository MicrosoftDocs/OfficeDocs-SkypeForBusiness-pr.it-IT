---
title: Consentire agli utenti di contatti esterni Skype per gli utenti aziendali
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: 'Informazioni su come configurare Skype for Business consentire agli utenti di comunicare agli utenti di un''altra organizzazione o consentire a tali contatti esterni. '
ms.openlocfilehash: e21b89c24618d2296dc44766b8d6ddbd3d527ef7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Consentire agli utenti di contatti esterni Skype per gli utenti aziendali

> [!NOTE]
> Skype per la federazione Business non è disponibile per Office 365 gestito dal 21Vianet e organizzazioni Germania di Office 365. 
  
Utilizzare la procedura descritta in questo articolo, se:
  
- In un'azienda sono presenti utenti in domini diversi. Ad esempio Rob@ContosoEast.com e Ann@ContosoWest.com.
    
- Le persone che si desidera all'interno dell'organizzazione di utilizzare Skype for Business per i contatti nelle aziende specifiche esterni all'organizzazione.
    
-Si desidera avevano in tutto il mondo che utilizza Skype per le aziende siano in grado di trovare e contattare un utente, utilizzando l'indirizzo di posta elettronica. Se si e è possibile utilizzare il valore predefinito Skype per le impostazioni di Business, questo funzionerà automaticamente. In caso contrario, è necessario assicurarsi che la relativa configurazione non viene bloccata del dominio.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Abilitare le comunicazioni aziendali to business per gli utenti
<a name="bk_preview"> </a>

In Office 365 a tale scopo, è necessario disporre [delle autorizzazioni di amministratore](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) .
  
1. Accedere con l'account di amministrazione di Office 365. 
    
2. Nell'interfaccia di amministrazione di Office 365 andare a **Admin Center** > **Skype per le aziende**.
    
    ![Scegliere Skype per interfaccia di amministrazione di Business.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. **Skype per interfaccia di amministrazione di Business**, selezionare **organizzazione** > **comunicazioni esterne**.
    
4. Per configurare la comunicazione con un aziendali specifici o agli utenti in un altro dominio, nella casella a discesa fare clic **su solo per domini consentiti**.
    
    In alternativa, se si desidera consentire le comunicazioni con tutti gli altri partecipanti in tutto il mondo è Apri Skype per i criteri aziendali, scegliere **su ad eccezione dei domini bloccati**. Questo è l'impostazione predefinita.
    
5. In **domini consentiti o bloccati**, scegliere **+** e aggiungere il nome del dominio che si desidera consentire.
    
6. Verificare che l'amministratore all'interno dell'organizzazione è la stessa procedura loro **Skype per interfaccia di amministrazione di Business**. Ad esempio, nel loro elenco **domini consentiti** proprio amministratore deve immettere il dominio per la propria azienda.
    
7. Se si utilizza Windows Firewall, Skype per le aziende apre le porte necessarie automaticamente.
    
    Se l'organizzazione utilizza una soluzione di firewall diverso per limitare i computer della rete di connettersi a Internet, verificare che i computer client siano in grado di accedere ai seguenti [intervalli di indirizzi IP e gli URL di Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges). Ciò potrebbe essere necessario aggiungere i nomi FQDN per l'uscita elenco Consenti di firewall o proxy di configurazione dell'infrastruttura: ** \*. api.skype.com**, \* **. users.storage.live.com**e **graph.skype.com**. Per istruzioni su come aprire le porte del firewall, consultare la documentazione fornita con esso.
    
    Per un elenco di tutte le porte, è necessario aprire, vedere [Office 365 URL e intervalli di indirizzi IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).
    
8. **ATTENDERE fino a 24 ore da TESTARE**. Ogni volta che si modificano le impostazioni di comunicazioni esterne, può richiedere fino a 24 ore per le modifiche da popolare in tutti i data center.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) è possibile consentire agli utenti di cercare e messaggistica immediata con tutti gli utenti Skype, app consumer gratuita! Per ulteriori informazioni, vedere [Skype consente agli utenti aziendali aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Risoluzione dei problemi
<a name="bk_preview"> </a>

 **Il problema più comune persone verificano durante l'impostazione di comunicazione business to business otterrà le [Office 365 URL e intervalli di indirizzi IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) destro.**
  
Per testare l'installazione, è necessario un contatto in Skype per le aziende che non sono protetti dal firewall aziendale.
  
1. Dopo aver modificare le impostazioni di comunicazioni esterne, **ATTENDERE fino a 24 ore a TEST**.
    
2. In Skype per le aziende, cercare il contatto in Skype per le aziende e inviare una richiesta a chat.
    
    Se viene visualizzato un messaggio in cui non è stato inviato a causa di politica aziendale, è necessario fare doppio clic di [Office 365 URL e intervalli di indirizzi IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Chiedere la Skype per contatto commerciale per inviare una richiesta a chat. Se non si ricevono le proprie richieste, il problema è le impostazioni del firewall (presupponendo che hai già confermato che le relative impostazioni di firewall siano corrette).
    
4. Per verificare se il problema è firewall, è passare a una posizione wifi non protetti dal firewall, ad esempio un Internet café e utilizzare Skype for Business per inviare una richiesta al contatto alla chat. Se il messaggio viene inviato disponibili, ma non quando si è in ufficio, si conosce il problema è firewall.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Come individuare altri utenti e sono disponibili durante la connessione con un'altra business
<a name="bk_preview"> </a>

Dopo aver abilitato le comunicazioni esterne con altri Skype per gli utenti aziendali, gli utenti possano trovare Skype federati per gli utenti aziendali di ricercare il nome di accesso: ad esempio Rob@contoso.com. È necessario quindi aggiungere la persona all'elenco dei contatti.
  
![Per individuare un utente in un'azienda federata, è necessario cercare l'indirizzo di posta elettronica (si tratta in genere anche il nome di accesso).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Suggerimenti sull'impostazione delle comunicazioni con aziende federate
<a name="bk_preview"> </a>

- Per configurare la federazione tra Skype per 2015 Business e Skype Business online, vedere questo articolo di TechNet: [configurazione della federazione con Skype Business online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Per configurare la federazione tra Lync e Skype Business online, vedere questo articolo di TechNet: [Configurazione del supporto per la federazione per un cliente di Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Quando si comunica tra loro due Skype per gli utenti aziendali di Office 365 in domini separati, possono utilizzare solo Skype per le caratteristiche (ad esempio, le conversazioni video o condivisione del desktop) che vengono attivate in entrambe le organizzazioni.
    
- Se un Skype per utenti Business all'interno dell'organizzazione è collocato in un In locale o conservazione per controversia legale, le conversazioni di messaggistica immediata tra l'utente e altre Skype per utenti Business o Skype verranno salvate nel **Degli elementi recuperabili** nella propria cassetta postale. Le conversazioni non vengono salvate nella cartella **Cronologia conversazioni** nella cassetta postale.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Disattivare le comunicazioni esterne per specifici utenti
<a name="bk_preview"> </a>

Dopo aver abilitato le comunicazioni esterne per un'intera azienda, è possibile disattivare lo per solo a utenti specifici.
  
1. Accedere con l'account di amministrazione di Office 365.
    
2. Nell'interfaccia di amministrazione di Office 365 accedere agli **utenti** > **utenti attivi**.
    
3. Nell'elenco di utenti, scegliere l'utente e quindi, in **Altre impostazioni**, fare clic su **Modifica Skype per le proprietà di Business**.
    
    ![Scegliere Skype per le aziende](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. **Skype per interfaccia di amministrazione di Business**, scegliere **comunicazioni esterne**.
    
    Nella pagina **Opzioni di** tutte le scelte verrà selezionate. Deselezionare le comunicazioni da disattivare. Nell'immagine seguente viene illustrato che Jakob saranno in grado di comunicare con utenti di altre aziende attendibili, ma non con altri utenti Skype.
    
    ![Scegliere contatti esterni](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Scegliere **Save**.
    
> [!NOTE]
> Potrebbe essere necessario attendere fino a 24 ore rendere effettive le modifiche. 
  


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Argomenti correlati
<a name="bk_preview"> </a>

[Configurare Skype for Business online](set-up-skype-for-business-online.md)
  
[Consentire Skype per gli utenti aziendali di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)
  

