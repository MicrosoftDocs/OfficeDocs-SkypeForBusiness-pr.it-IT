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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: "Scopri come consentire alle persone che usano Skype for Business di contattare Skype for Business utenti esterni all'organizzazione e aggiungerli al loro elenco di contatti. "
ms.openlocfilehash: 77fb8098e7adeebd4267aed7f21153b20abd661b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594840"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Consentire agli utenti di Skype for Business di aggiungere contatti Skype

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Con Skype for Business, gli utenti possono cercare e messaggi istantanei con chiunque usi Skype, l'app gratuita! Questo articolo spiega cosa è necessario fare in modo che possano aggiungere Skype contatti. 
  
Per eseguire questa [operazione,](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) è Microsoft 365 o Office 365 autorizzazioni di amministratore.

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**
  
1. Accedere con l'account Microsoft 365 o Office 365 amministratore di [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) .
    
2. Nell'interfaccia di amministrazione passare a **Interfaccia di amministrazione**  >  **Skype for Business**. 
    
    ![Scegliere l'Skype for Business di amministrazione.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Nell'**interfaccia di amministrazione di Skype for Business** scegliere **Organizzazione** > **Comunicazioni esterne**. 
    
4. Per impostazione predefinita, gli utenti possono comunicare con tutte le altre persone del mondo che usano Skype for Business (presupponendo che il firewall sia stato configurato per consentire questa operazione). 
    
    ![Scegliere Consenti agli utenti di Skype for Business comunicare con Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Se si vuole che gli utenti chattino con Skype utenti, ma non si vuole che chattino con altri utenti che usano Skype for Business, scegliere Sì solo per i **domini consentiti.** Quando si abilita il contatto con Skype utenti, skype.com viene aggiunto automaticamente come dominio consentito dietro le quinte. 
    
    Se si vuole consentire ai contatti di tutte le altre aziende del mondo di usare Skype for Business, ad eccezione di quelli specifici, scegliere Sì ad eccezione dei domini bloccati **e** scegliere di aggiungere **+** tali domini. Tutti saranno in grado di contattare l'utente tranne le persone di questi domini specifici. Alcune aziende potrebbero scegliere questa opzione, ad esempio, se sono in controversia legale e devono assicurarsi che non ci siano contatti con l'altra azienda.
    
5. Scegliere Consenti agli utenti di Skype for Business comunicare con Skype **utenti esterni all'organizzazione.** 
    
6.  Se si usa Windows Firewall, Skype for Business automaticamente le porte necessarie.
    
    Se l'organizzazione usa un'altra soluzione per limitare la connessione a Internet dei computer della rete, verificare che i computer client siano in grado di accedere a tutti gli indirizzi IP e gli [URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per la connettività Skype e la ricerca nella directory Skype. Potrebbe essere necessario aggiungerli all'elenco di indirizzi consentiti in uscita nella configurazione del firewall o dell'infrastruttura proxy.
    
7. **ATTENDERE FINO A 24 ORE PER TESTARE**. Ogni volta che si modificano le impostazioni delle comunicazioni esterne, possono essere necessarie fino a 24 ore prima che le modifiche possano essere popolate in tutti i data center.
    
8. Mostra agli utenti come trovare e aggiungere Skype contatti all'elenco di Skype for Business contatti. Selezionare Cerca [persone in Skype for Business](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).
    
## <a name="test-and-troubleshoot"></a>Testare e risolvere i problemi

Per testare la configurazione, è necessario un contatto Skype che non sia dietro il firewall aziendale. Possono essere connessi a Skype con un account Gmail, un account Outlook.com o un altro tipo di account di posta elettronica.
  
1. Dopo aver modificato le impostazioni delle comunicazioni esterne, **ATTENDERE FINO A 24 ORE PER VERIFICARE**.
    
2. Disconnettersi da Skype for Business quindi accedere di nuovo in modo da visualizzare l'opzione per cercare nella directory Skype. 
    
    ![Quando Skype è evidenziata, è possibile cercare le persone che hanno Skype account.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. In Skype for Business, cercare il contatto in Skype e inviare una richiesta di chat. 
    
    Se viene visualizzato il messaggio che non è stato possibile inviare a causa dei criteri aziendali, è necessario verificare le impostazioni [del firewall.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) 
    
4. Un altro modo per verificare se il problema è il firewall è passare a una posizione WiFi non dietro il firewall, ad esempio una caffetteria, e usare Skype for Business per inviare una richiesta al contatto di Skype per chattare. 
    
   - **Se hai inviato il tuo Skype contatta una richiesta** e non l'ha mai ricevuta, chiedigli di inviarti una richiesta di chat. Se il problema stava stabilendo una connessione tra Skype e Skype for Business, questo spesso lo risolve.
    
   - Ora, se il messaggio viene inviato al bar, ma non al lavoro, il problema è il firewall. 
    
## <a name="what-you-can-and-cant-do"></a>Cosa si può e non si può fare

- **Skype for Business in Mac** non è possibile cercare e comunicare con Skype contatti.
    
- Quando la ricerca nella directory è abilitata, è possibile cercare e trovare Skype e Skype for Business utenti. Se per qualche motivo non è possibile trovarli eseguendo una ricerca nella directory, è possibile inviare una richiesta di contatto e chiedere loro di accedere a Skype e accettarla, in modo da potervi inviare messaggi istantanei. 
    
- Non è possibile consentire la connettività di messaggistica istantanea con altri provider di messaggistica istantanea, ad esempio Google o Facebook. Non è possibile usare i messaggi Skype for Business per inviare SMS al cellulare.

- Non è possibile registrare chiamate audio o video tra un contatto Skype contatto Skype for Business contatto.
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>Quali funzionalità sono disponibili quando si aggiungono Skype contatti?

Skype i contatti che hanno eseguito l'accesso con il proprio account Microsoft (in precedenza Windows Live ID) possono ottenere alcune funzionalità, ma non tutte, quando parlano con gli utenti Skype for Business utenti.
  
|**Disponibile con Skype contatti**|**Non disponibile con i Skype contatti**|
|:-----|:-----|
| Conversazioni video <br/>  Messaggistica istantanea da persona a persona <br/>  Icone di presenza <br/> | Conversazioni di messaggistica istantanea tra più parti <br/>  Conversazioni audio e video con tre o più persone <br/>  Condivisione di desktop e programmi <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Argomenti correlati

[Consentire agli utenti di contattare utenti Skype for Business esterni](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

  
 
