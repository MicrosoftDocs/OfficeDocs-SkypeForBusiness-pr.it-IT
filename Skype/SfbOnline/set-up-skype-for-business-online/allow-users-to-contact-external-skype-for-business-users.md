---
title: Permettere agli utenti di contattare utenti Skype for Business esterni
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
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
description: "Scopri come configurare Skype for business per consentire agli utenti di parlare con gli utenti di un'altra organizzazione o di consentire loro di accedere ai contatti esterni. "
ms.openlocfilehash: 3656038efa660db0b63f382908f4de5a8b7172d4
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344561"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Permettere agli utenti di contattare utenti Skype for Business esterni

> [!NOTE]
> La Federazione di Skype for business non è disponibile per Office 365 gestito da 21Vianet e dalle organizzazioni di Office 365 Germany. 
  
Seguire i passaggi di questo articolo quando:
  
- Si hanno utenti su domini diversi nell'azienda. Ad esempio, Rob@ContosoEast.com e Ann@ContosoWest.com.
    
- Si vuole che gli utenti dell'organizzazione usino Skype for business per contattare persone di aziende specifiche all'esterno dell'organizzazione.
    
- Si vuole che chiunque altro al mondo usi Skype for business sia in grado di trovare e contattare l'utente, usando l'indirizzo di posta elettronica. Se si usano le impostazioni predefinite di Skype for business, questo funzionerà automaticamente. In caso contrario, è necessario assicurarsi che la configurazione non blocchi il dominio.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Abilitare le comunicazioni business-to-business per gli utenti
<a name="bk_preview"> </a>

Per eseguire questa operazione, è necessario disporre [delle autorizzazioni di amministratore](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in entrambe le organizzazioni.

![Icona che mostra il logo](../images/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di teams**
  
1. Accedere con l'account di amministratore di Office 365. 
    
2. Nell'interfaccia di amministrazione di Office 365 accedere a **** > **Teams**di interfaccia di amministrazione.
    
    ![Scegliere l'amministratore di teams.](../images/MS-Teams-Admin.png)
  
3. Nel **centro teams**scegliere **Skype** > **legacy Portal** 
 ![scegliere il portale legacy di SFB.](../images/SFBlegacy-size65.png)
 
4. Nell'interfaccia di **amministrazione di Skype for business** scegli **** > **comunicazioni esterne**dell'organizzazione.
5. Per configurare la comunicazione con un'azienda specifica o con utenti di un altro dominio, nella casella a discesa scegliere **solo per i domini**consentiti.
    
    In alternativa, se vuoi abilitare la comunicazione con tutti gli altri utenti del mondo che hanno aperto i criteri di Skype for business, scegli attivato **eccetto i domini bloccati**. Questa è l'impostazione predefinita.
    
6. In **domini bloccati o**consentiti **+** scegliere e aggiungere il nome del dominio che si vuole consentire.
    
7. Verificare che l'amministratore dell'altra organizzazione effettui gli stessi passaggi nell'interfaccia di **amministrazione di Skype for business**. Nell'elenco dei **domini** consentiti, ad esempio, l'amministratore deve immettere il dominio per l'azienda.
    
8. Se si usa Windows Firewall, Skype for Business apre automaticamente le porte necessarie.
    
    Se l'organizzazione usa una soluzione firewall diversa per limitare la connessione a Internet da parte dei computer della rete, assicurarsi che i computer client siano in grado di accedere agli [URL e agli intervalli di indirizzi IP di Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)seguenti. Potrebbe essere necessario aggiungere i nomi di dominio completi all'elenco Consenti in uscita nella configurazione del firewall o dell'infrastruttura proxy: ** \*. API.Skype.com**, \* **. Users.storage.Live.com**e **Graph.Skype.com**. Per istruzioni su come aprire queste porte nel firewall, controllare la documentazione fornita con esso.
    
    Per un elenco di tutte le porte che è necessario aprire, vedere [URL e intervalli di indirizzi IP di Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).

9. Verificare che anche l'amministratore dell'organizzazione abbia seguito questi passaggi.
    
10. **Attendere fino a 24 ore per eseguire il test**. Ogni volta che si modificano le impostazioni di comunicazione esterna, è possibile che le modifiche vengano inserite in tutti i centri dati fino a 24 ore.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) è possibile consentire agli utenti di cercare e inviare messaggi istantanei con tutti coloro che usano Skype, l'app consumer gratuita. Per altre informazioni, vedere [consentire agli utenti di Skype for business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Test e risoluzione dei problemi
<a name="bk_preview"> </a>

 **Il problema più comune che si verifica quando si configura la comunicazione business-to-business è ottenere gli [URL di Office 365 e gli intervalli di indirizzi IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) giusti.**
  
Per testare la configurazione, è necessario un contatto in Skype for business che non si trova dietro il firewall aziendale.
  
1. Dopo aver modificato le impostazioni di comunicazione esterna, **attendere fino a 24 ore per**eseguire il test.
    
2. In Skype for business cerca il tuo contatto in Skype for business e invia una richiesta di chat.
    
    Se viene visualizzato un messaggio che non può essere inviato a causa di criteri aziendali, è necessario effettuare un doppio controllo sugli [URL e gli intervalli di indirizzi IP di Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Chiedere al contatto Skype for business di inviare una richiesta di chat. Se non si riceve la richiesta, il problema è che le impostazioni del firewall (presumendo che abbiano già confermato le impostazioni del firewall siano corrette).
    
4. Un altro modo per verificare se il problema è il firewall consiste nell'accedere a una posizione WiFi non dietro il firewall, ad esempio un coffee shop, e usare Skype for business per inviare una richiesta al contatto per la chat. Se il messaggio passa da lì, ma non quando si è al lavoro, si sa che il problema è il firewall.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Come trovare altre persone e trovarle durante la connessione con un'altra azienda
<a name="bk_preview"> </a>

Dopo aver abilitato le comunicazioni esterne con altri utenti di Skype for business, gli utenti possono trovare gli utenti di Skype for business federati per cercare il nome di accesso: ad esempio, Rob@contoso.com. Sarà quindi necessario aggiungere la persona al proprio elenco di contatti.
  
![Per trovare un utente in un'azienda federata, è necessario cercare l'indirizzo di posta elettronica (in genere è anche il nome di accesso).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Suggerimenti per la configurazione delle comunicazioni con le aziende federate
<a name="bk_preview"> </a>

- Per configurare la Federazione tra Skype for business 2015 e Skype for business online, vedere questo articolo: [configurare la Federazione con Skype for business online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Per configurare la Federazione tra Lync e Skype for business online, vedere questo articolo: [configurazione del supporto federativo per un cliente di Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Quando due utenti di Skype for business in Office 365 comunicano tra loro su domini separati, possono usare solo le caratteristiche di Skype for business (ad esempio, conversazioni video o condivisione desktop) attivate in entrambe le organizzazioni.
    
- Se un utente di Skype for business nell'organizzazione viene inserito in un blocco sul posto o in una controversia legale, le conversazioni ISTANTANEe tra l'utente e gli altri utenti di Skype for business o Skype verranno salvate in **elementi ripristinabili** nella cassetta postale. Le conversazioni non vengono salvate nella cartella **Cronologia conversazioni** nella cassetta postale.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Disattivare le comunicazioni esterne per individui specifici
<a name="bk_preview"> </a>

Dopo aver abilitato le comunicazioni esterne per l'intera azienda, è possibile disattivarle solo per singoli utenti specifici.
  
1. Accedere con l'account di amministratore di Office 365.
    
2. Nell'interfaccia di amministrazione di Office 365 passa a **** > utenti**attivi**.
    
3. Nell'elenco degli utenti scegliere l'utente e quindi, in **altre impostazioni**, fare clic su **modifica proprietà Skype for business**.
    
    ![Scegliere Skype for business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. Nell'interfaccia di **amministrazione di Skype for business**scegli **comunicazioni esterne**.
    
    Nella pagina **Opzioni** verranno selezionate tutte le scelte. Deselezionare le comunicazioni che si desidera disabilitare. L'immagine seguente mostra che Jakob sarà in grado di comunicare con persone di altre aziende attendibili, ma non con altri utenti Skype.
    
    ![Scegliere contatti esterni](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Scegliere **Save**.
    
> [!NOTE]
> Potrebbe essere necessario attendere fino a 24 ore affinché le modifiche abbiano effetto. 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Argomenti correlati
<a name="bk_preview"> </a>

[Configurare Skype for Business online](set-up-skype-for-business-online.md)
  
[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
