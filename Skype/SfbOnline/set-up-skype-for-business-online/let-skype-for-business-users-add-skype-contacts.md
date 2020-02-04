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
description: "Informazioni su come consentire alle persone che usano Skype for business di contattare utenti Skype for business all'esterno dell'organizzazione e aggiungerli al proprio elenco di contatti. "
ms.openlocfilehash: d6251e8e86527172e6818d11b1e07da892b4b0ef
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692881"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Consentire agli utenti di Skype for Business di aggiungere contatti Skype

Con Skype for business, gli utenti possono cercare e inviare messaggi istantanei con tutti coloro che usano Skype, l'app gratuita. In questo articolo vengono illustrate le operazioni da eseguire in modo che possano aggiungere contatti Skype. 
  
Per eseguire questa operazione, è necessario disporre [delle autorizzazioni di amministratore](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365.

![Icona che mostra il logo](../images/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business**
  
1. Accedere con l'account di amministratore di Office 365 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)all'indirizzo.
    
2. Nell'interfaccia di amministrazione accedere a interfaccia di **Amministrazione** > di**Skype for business**. 
    
    ![Scegliere l'interfaccia di amministrazione di Skype for business.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Nell'interfaccia di **amministrazione di Skype for business**scegli **** > **comunicazioni esterne**dell'organizzazione. 
    
4. Per impostazione predefinita, gli utenti possono comunicare con tutte le altre persone del mondo che usano Skype for business (supponendo che il firewall sia stato configurato per consentire questa operazione). 
    
    ![Scegli consentire agli utenti di usare Skype for business per comunicare con Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Se vuoi che gli utenti possano chattare con gli utenti Skype, ma non vuoi che vengano chattati con altri che usano Skype for business, scegli **solo per i domini consentiti**. Quando si Abilita il contatto con utenti Skype, skype.com viene automaticamente aggiunto come dominio consentito dietro le quinte. 
    
    Se vuoi consentire il contatto di tutte le altre aziende del mondo usando Skype for business, eccetto quelle specifiche, scegli attivato **eccetto i domini bloccati**e scegli **+** di aggiungere tali domini. Tutti saranno in grado di contattare l'utente, eccetto gli utenti di questi specifici domini. Alcune aziende potrebbero scegliere questa opzione, ad esempio se sono in contenzioso ed è necessario assicurarsi che non ci siano contatti con l'altra azienda.
    
5. Scegli **consentire alle persone di usare Skype for business per comunicare con gli utenti Skype all'esterno dell'organizzazione**. 
    
6.  Se si usa Windows Firewall, Skype for Business apre automaticamente le porte necessarie.
    
    Se l'organizzazione usa un'altra soluzione per limitare la connessione a Internet da parte dei computer della rete, assicurarsi che i computer client siano in grado di accedere a tutti gli [indirizzi IP e agli URL](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per la connettività Skype e la ricerca nella directory Skype. Potrebbe essere necessario aggiungerli all'elenco Consenti in uscita nella configurazione del firewall o dell'infrastruttura proxy.
    
7. **Attendere fino a 24 ore per eseguire il test**. Ogni volta che si modificano le impostazioni di comunicazione esterna, è possibile che le modifiche vengano inserite in tutti i centri dati fino a 24 ore.
    
8. Mostra agli utenti come trovare e aggiungere contatti Skype all'elenco dei contatti di Skype for business. Puntali alla [ricerca di persone in Skype for business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).
    
## <a name="test-and-troubleshoot"></a>Test e risoluzione dei problemi

Per testare la configurazione, è necessario un contatto su Skype che non si trova dietro il firewall aziendale. Possono essere connessi a Skype usando un account di Gmail, un account di Outlook.com o un altro tipo di account di posta elettronica.
  
1. Dopo aver modificato le impostazioni di comunicazione esterna, **attendere fino a 24 ore per**eseguire il test.
    
2. Disconnettersi da Skype for business e quindi eseguire di nuovo l'accesso per visualizzare l'opzione per cercare nella directory Skype. 
    
    ![Quando viene evidenziata la directory Skype, è possibile cercare persone con account Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. In Skype for business cercare il contatto in Skype e inviare una richiesta di chat. 
    
    Se viene visualizzato il messaggio che non è stato possibile inviare a causa di criteri aziendali, è necessario effettuare un doppio controllo sulle [impostazioni del firewall](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). 
    
4. Un altro modo per verificare se il problema è il firewall consiste nell'accedere a una posizione WiFi non dietro il firewall, ad esempio un coffee shop, e usare Skype for business per inviare una richiesta al contatto Skype per chattare. 
    
   - **Se il contatto Skype è stato inviato a una richiesta e non è mai stato ricevuto**, chiedere loro di inviare una richiesta di chat. Se il problema è stato stabilire una connessione tra Skype e Skype for business, che spesso lo risolve.
    
   - Ora, se il messaggio passa al Coffee Shop, ma non quando sei al lavoro, allora sai che il problema è il tuo firewall. 
    
## <a name="what-you-can-and-cant-do"></a>Cosa si può o non si può fare

- **Skype for business per Mac** non ha la possibilità di cercare e comunicare con i contatti Skype.
    
- Quando la ricerca directory è abilitata, è possibile cercare e trovare utenti Skype e Skype for business. Se per qualche motivo non è possibile trovarli eseguendo una ricerca nella directory, è possibile inviare una richiesta di contatto e quindi accedervi in Skype e accettarla, in modo che sia possibile inviarla tramite chat. 
    
- Non è possibile consentire la connettività di messaggistica istantanea con altri provider di messaggistica istantanea, ad esempio Google o Facebook. Non è possibile usare Skype for business per inviare messaggi di testo tramite telefono cellulare.

- Non è possibile registrare chiamate audio o video tra un contatto Skype e un contatto Skype for business.
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>Quali funzionalità sono disponibili quando si aggiungono contatti Skype?

I contatti di Skype che hanno effettuato l'accesso con il proprio account Microsoft (in precedenza Windows Live ID) possono ottenere alcune funzionalità, ma non tutte, quando parlano con gli utenti di Skype for business.
  
|**Disponibile con i contatti Skype**|**Non disponibile con i contatti Skype**|
|:-----|:-----|
| Conversazioni video <br/>  Messaggistica istantanea da persona a persona <br/>  Icone di presenza <br/> | Conversazioni di messaggistica istantanea con più partecipanti <br/>  Conversazioni audio e video con tre o più persone <br/>  Condivisione di desktop e programmi <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Argomenti correlati

[Consentire agli utenti di contattare utenti Skype for Business esterni](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

  
 
