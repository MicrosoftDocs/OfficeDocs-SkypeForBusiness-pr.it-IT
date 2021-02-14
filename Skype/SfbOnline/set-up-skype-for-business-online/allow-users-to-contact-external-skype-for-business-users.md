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
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: "Scopri come configurare Skype for Business in modo che gli utenti parlino con gli utenti di un'altra organizzazione o che i contatti esterni parlino con loro. "
ms.openlocfilehash: d9b3be381432fa95962df7a5a58ea9d81e223fc4
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625052"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Permettere agli utenti di contattare utenti Skype for Business esterni
  
Seguire i passaggi descritti in questo articolo quando:
  
- Gli utenti dell'azienda hanno utenti con domini diversi. Ad esempio, Rob@ContosoEast.com e Ann@ContosoWest.com.

- Si desidera che le persone dell'organizzazione usino Skype for Business per contattare persone di aziende specifiche all'esterno dell'organizzazione.

- Si desidera che chiunque altro nel mondo che usa Skype for Business possa trovarti e contattarti utilizzando il tuo indirizzo e-mail. Se tu e loro usate le impostazioni predefinite di Skype for Business, questa funzionerà automaticamente. In caso contrario, devono verificare che la loro configurazione non blocchi il dominio.

## <a name="enable-business-to-business-communications-for-your-users"></a>Abilitare le comunicazioni business-to-business per gli utenti

<a name="bk_preview"> </a>

Per eseguire questa [comunicazione,](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) è necessario avere autorizzazioni di amministratore in Microsoft 365 o Office 365 in entrambe le organizzazioni.

![Icona che mostra il logo di Microsoft Teams ](../images/teams-logo-30x30.png) **tramite l'interfaccia di amministrazione di Teams**
  
1. Accedere con l'account di amministratore di Microsoft 365 o Office 365.

2. Nell'interfaccia di amministrazione passare a **Team delle interfaccia di**  >  **amministrazione.**

    ![Scegliere l'amministratore di Teams.](../images/MS-Teams-Admin.png)
  
3. Nel centro **Teams,** scegli **il portale legacy di** >  
  ![ Skype, scegli il portale legacy di SfB.](../images/SFBlegacy-size65.png)

4. Nell'**interfaccia di amministrazione di Skype for Business** scegliere **Organizzazione** > **Comunicazioni esterne**.
5. Per configurare la comunicazione con una specifica azienda o con utenti in un altro dominio, nella casella di riepilogo a discesa scegliere **Attiva solo per i domini consentiti**.

    OPPURE, se desideri consentire la comunicazione con chiunque altro nel mondo abbia politiche di Skype for Business, scegli Attivato ad eccezione **dei domini bloccati.** Questa è l'impostazione predefinita.

6. In **Domini bloccati o consentiti** scegliere e aggiungere il nome del dominio che si vuole **+** consentire.

7. Assicurati che l'amministratore dell'altra organizzazione eserciti questi stessi passaggi nell'interfaccia **di amministrazione di Skype for Business.** Ad esempio, **nell'elenco dei domini consentiti,** l'amministratore deve immettere il dominio per l'azienda.

8. Se si usa Windows Firewall, Skype for Business apre automaticamente le porte richieste.

    Se l'organizzazione usa una soluzione firewall diversa per limitare la connessione a Internet dei computer della rete, verificare che i computer client siano in grado di accedere ai seguenti URL e intervalli di indirizzi IP per [Office 365.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) A questo scopo può essere necessario aggiungere gli FQDN all'elenco degli elementi consentiti in uscita nella configurazione dell'infrastruttura del firewall o del proxy: con estensione **\* api.skype.com,** \* **users.storage.live.com** e **graph.skype.com.** Per istruzioni su come aprire queste porte nel firewall, consultare la documentazione fornita con il firewall.

    Per un elenco di tutte le porte che è necessario aprire, vedere URL e intervalli di indirizzi [IP per Office 365.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)

9. Assicurarsi che anche l'amministratore dell'organizzazione abbia seguito questa procedura.

10. **ATTENDI FINO A 24 ORE PER IL TEST.** Quando si modificano le impostazioni per le comunicazioni esterne, possono essere necessarie fino a 24 ore prima che le modifiche verranno popolate in tutti i data center.

![Skype È possibile consentire agli utenti di cercare e usare la messaggistica istantanea con chiunque usi ](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Skype, l'app consumer gratuita. Per ulteriori informazioni, consulta [Consentire agli utenti Skype for Business di aggiungere contatti Skype.](let-skype-for-business-users-add-skype-contacts.md)
  
## <a name="test-and-troubleshoot"></a>Test e risoluzione dei problemi

<a name="bk_preview"> </a>

 **Il problema più comune che si verifica quando si configura la comunicazione business-to-business è ottenere i propri URL e intervalli di indirizzi IP per [Office 365.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)**
  
Per testare la configurazione, devi avere un contatto in Skype for Business che non sia dietro il firewall della tua azienda.
  
1. Dopo aver modificato le impostazioni per le comunicazioni esterne, **ATTENDI FINO A 24 ORE PER TESTARE.**

2. In Skype for Business, cerca il tuo contatto in Skype for Business e invia una richiesta di chat.

    Se viene visualizzato un messaggio che indica che non è stato possibile inviare il messaggio a causa dei criteri aziendali, è necessario verificare gli URL e gli intervalli di indirizzi IP per [Office 365.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)

3. Chiedi al tuo contatto Skype for Business di inviarti una richiesta di chat. Se non si riceve la richiesta, il problema sono le impostazioni del firewall, supponendo di aver già verificato che le impostazioni firewall dell'altra organizzazione siano corrette.

4. Un altro modo per verificare se il problema è il tuo firewall è accedere a un wi-fi che non si trova dietro il firewall, ad esempio in un bar. Usare Skype for Business per inviare una richiesta di chat al proprio contatto. Se il messaggio viene inviato da lì, ma non quando sei al lavoro, allora il problema è il tuo firewall.

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Come trovare ed essere trovati quando ti contatti con un'altra azienda

<a name="bk_preview"> </a>

Dopo aver abilitato la comunicazione esterna con altri utenti Skype for Business, gli utenti possono trovare utenti Skype for Business federati cercando i loro nomi di accesso. Un esempio è Rob@contoso.com. La persona dovrà quindi essere aggiunta alla propria lista di contatti.
  
![Per trovare un utente in un'azienda federata, è necessario cercarne l'indirizzo di posta elettronica (in genere è anche il nome di accesso).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Suggerimenti sulla configurazione delle comunicazioni con le aziende federate

<a name="bk_preview"> </a>

- Per configurare la federazione tra Skype for Business 2015 e Skype for Business online, vedere questo articolo: Configurare la [federazione con Skype for Business online.](https://technet.microsoft.com/library/jj205126.aspx)

- Per configurare la federazione tra Lync e Skype for Business online, vedere questo articolo: Configurazione del supporto della federazione per [un cliente di Lync Online.](https://technet.microsoft.com/library/hh202193.aspx)

- Quando due utenti di Skype for Business in Microsoft 365 o Office 365 comunicano tra loro in domini separati, possono utilizzare solo le funzionalità di Skype for Business (ad esempio le conversazioni video o la condivisione del desktop) attivate in entrambe le organizzazioni.

- Se a un utente Skype for Business all'interno dell'organizzazione viene messo in stato di In-Place o blocco per controversia legale, tutte le conversazioni istantanee tra tale utente e altri utenti Skype for Business o Skype verranno salvate **in** Elementi ripristinabili nella propria cassetta postale. Queste conversazioni non vengono salvate nella **cartella** Cronologia conversazioni della propria cassetta postale.

## <a name="turn-off-external-communication-for-specific-individuals"></a>Disattivare la comunicazione esterna per persone specifiche

<a name="bk_preview"> </a>

Dopo aver abilitato la comunicazione esterna per l'intera azienda, è possibile disattivarla solo per individui specifici.
  
1. Accedere con l'account di amministratore di Microsoft 365 o Office 365.

2. Nell'interfaccia di amministrazione passare **a Utenti**  >  **attivi.**

3. Nell'elenco degli utenti, scegli l'utente e quindi, in Altre **impostazioni,** fai clic **su Modifica proprietà Skype for Business.**

    ![Scegli Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. **Nell'interfaccia di amministrazione di Skype for Business** scegli Comunicazioni **esterne.**

    Nella pagina **Opzioni** saranno selezionate tutte le opzioni. Cancellare le comunicazioni da disabilitare. L'immagine seguente mostra che Jakob sarà in grado di comunicare con persone di altre aziende attendibili, ma non con altri utenti Skype.

    ![Scegliere Contatti esterni](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Scegliere **Save**.

> [!NOTE]
> Per l'applicazione delle modifiche potrebbe essere necessario attendere fino a 24 ore.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Argomenti correlati

<a name="bk_preview"> </a>

[Configurare Skype for Business online](set-up-skype-for-business-online.md)
  
[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)
  