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
description: "Scopri come configurare Skype for Business per consentire agli utenti di parlare con utenti di un'altra organizzazione o lasciare che i contatti esterni parlino con loro. "
ms.openlocfilehash: 8acab73fec7337ee70cd8b5059b00df42e836e62
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093510"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Permettere agli utenti di contattare utenti Skype for Business esterni
  
Seguire la procedura descritta in questo articolo quando:
  
- Si hanno utenti di domini diversi nell'azienda. Ad esempio, Rob@ContosoEast.com e Ann@ContosoWest.com.

- Si vuole che le persone dell'organizzazione usino Skype for Business per contattare persone di specifiche aziende esterne all'organizzazione.

- Vuoi che chiunque altro al mondo che usa Skype for Business sia in grado di trovare e contattare l'utente usando il tuo indirizzo e-mail. Se tu e loro userai le impostazioni predefinite di Skype for Business, questa funzionerà automaticamente. In caso contrario, è necessario assicurarsi che la configurazione non blocchi il dominio.

## <a name="enable-business-to-business-communications-for-your-users"></a>Abilitare le comunicazioni business-to-business per gli utenti

<a name="bk_preview"> </a>

Per eseguire questa [comunicazione,](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) è necessario disporre delle autorizzazioni di amministratore in Microsoft 365 o Office 365 in entrambe le organizzazioni.

![Icona che mostra il logo di Microsoft Teams ](../images/teams-logo-30x30.png) **Usando l'interfaccia di amministrazione di Teams**
  
1. Accedere con l'account di amministratore di Microsoft 365 o Office 365.

2. Nell'interfaccia di amministrazione passare a **Admin Centers**  >  **Teams**.

    ![Scegliere l'amministratore di Teams.](../images/MS-Teams-Admin.png)
  
3. Nel centro **di Teams** scegliere **Portale legacy Skype** Scegli il portale Legacy >  
  ![ SfB.](../images/SFBlegacy-size65.png)

4. Nell'**interfaccia di amministrazione di Skype for Business** scegliere **Organizzazione** > **Comunicazioni esterne**.
5. Per configurare la comunicazione con una specifica azienda o con utenti in un altro dominio, nella casella di riepilogo a discesa scegliere **Attiva solo per i domini consentiti**.

    OPPURE, se si vuole abilitare la comunicazione con tutti gli altri utenti del mondo che hanno aperto i criteri di Skype for Business, scegliere Attivato ad eccezione **dei domini bloccati.** Questa è l'impostazione predefinita.

6. In **Domini bloccati o consentiti** scegliere e aggiungere il nome del dominio da **+** consentire.

7. Assicurati che l'amministratore dell'altra organizzazione eserciti gli stessi passaggi nell'interfaccia di amministrazione **di Skype for Business.** Ad esempio, **nell'elenco dei domini consentiti,** l'amministratore deve immettere il dominio per l'azienda.

8. Se si usa Windows Firewall, Skype for Business apre automaticamente le porte richieste.

    Se l'organizzazione usa una soluzione firewall diversa per limitare la connessione a Internet dei computer della rete, verificare che i computer client siano in grado di accedere agli URL e agli intervalli di indirizzi IP di [Office 365 seguenti.](/microsoftteams/office-365-urls-ip-address-ranges) Potrebbe essere necessario aggiungere gli FQDN all'elenco di indirizzi consentiti in uscita nella configurazione del firewall o dell'infrastruttura proxy: **\* .api.skype.com,** \* *_.users.storage.live.com_* e **graph.skype.com**. Per istruzioni su come aprire queste porte nel firewall, consultare la documentazione fornita con essa.

    Per un elenco di tutte le porte da aprire, vedere URL e intervalli di indirizzi [IP di Office 365.](/microsoftteams/office-365-urls-ip-address-ranges)

9. Assicurarsi che anche l'amministratore dell'organizzazione abbia seguito questa procedura.

10. **ATTENDERE FINO A 24 ORE PER TESTARE**. Quando si modificano le impostazioni delle comunicazioni esterne, possono essere necessarie fino a 24 ore prima che le modifiche possano essere popolate in tutti i data center.

![Skype È possibile consentire agli utenti di cercare e messaggi istantanei con tutti gli utenti ](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) che utilizzano Skype, l'app consumer gratuita. Per altre informazioni, consulta [Consentire agli utenti di Skype for Business di aggiungere contatti Skype.](let-skype-for-business-users-add-skype-contacts.md)
  
## <a name="test-and-troubleshoot"></a>Testare e risolvere i problemi

<a name="bk_preview"> </a>

 **Il problema più comune che le persone riscontrano quando si configurano le comunicazioni business-to-business è ottenere gli URL e gli intervalli di indirizzi IP di [Office 365](/microsoftteams/office-365-urls-ip-address-ranges) a destra.**
  
Per testare la configurazione, è necessario un contatto su Skype for Business che non sia dietro il firewall aziendale.
  
1. Dopo aver modificato le impostazioni delle comunicazioni esterne, **ATTENDERE FINO A 24 ORE PER VERIFICARE**.

2. In Skype for Business, cerca il tuo contatto in Skype for Business e invia una richiesta di chat.

    Se viene visualizzato un messaggio che indica che non è stato possibile inviare il messaggio a causa dei criteri aziendali, è necessario verificare gli URL e gli intervalli di indirizzi IP di [Office 365.](/microsoftteams/office-365-urls-ip-address-ranges)

3. Chiedi al tuo contatto Skype for Business di inviarti una richiesta di chat. Se non si riceve la richiesta, il problema sono le impostazioni del firewall, supponendo di aver già verificato che le impostazioni firewall dell'altra organizzazione siano corrette.

4. Un altro modo per verificare se il problema è il firewall è passare a una posizione WiFi non dietro il firewall, ad esempio una caffetteria. Usa Skype for Business per inviare una richiesta al tuo contatto per chattare. Se il messaggio viene inviato, ma non al lavoro, il problema è il firewall.

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Come trovare altri utenti ed essere trovati quando ci si connette con un'altra azienda

<a name="bk_preview"> </a>

Dopo aver abilitato la comunicazione esterna con altri utenti di Skype for Business, gli utenti possono trovare gli utenti federati di Skype for Business cercando i nomi di accesso. Un esempio è Rob@contoso.com. Dovrà quindi aggiungere la persona all'elenco dei contatti.
  
![Per trovare un utente in un'azienda federata, è necessario cercarne l'indirizzo di posta elettronica ,in genere anche il nome di accesso.](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Suggerimenti sulla configurazione delle comunicazioni con le aziende federate

<a name="bk_preview"> </a>

- Per configurare la federazione tra Skype for Business 2015 e Skype for Business online, vedere questo articolo: Configurare la [federazione con Skype for Business online.](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)

- Per configurare la federazione tra Lync e Skype for Business online, vedere questo articolo: Configurazione del supporto della federazione [per un cliente di Lync Online.](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)

- Quando due utenti di Skype for Business in Microsoft 365 o Office 365 comunicano tra loro in domini separati, possono usare solo le funzionalità di Skype for Business (ad esempio, conversazioni video o condivisione desktop) attivate in entrambe le organizzazioni.

- Se un utente Skype for Business nella tua organizzazione viene messo in un blocco In-Place o per controversia legale, tutte le conversazioni istantanee tra quell'utente e altri utenti Skype for Business o Skype verranno salvate **in** Elementi ripristinabili nella loro cassetta postale. Queste conversazioni non vengono salvate nella cartella **Cronologia** conversazioni della cassetta postale.

## <a name="turn-off-external-communication-for-specific-individuals"></a>Disattivare le comunicazioni esterne per utenti specifici

<a name="bk_preview"> </a>

Dopo aver abilitato la comunicazione esterna per l'intera azienda, è possibile disattivarla solo per utenti specifici.
  
1. Accedere con l'account di amministratore di Microsoft 365 o Office 365.

2. Nell'interfaccia di amministrazione passare a **Utenti**  >  **utenti attivi**.

3. Nell'elenco degli utenti scegliere l'utente e quindi, in **Altre impostazioni,** fare clic **su Modifica proprietà di Skype for Business.**

    ![Scegli Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. **Nell'interfaccia di amministrazione di Skype for Business** scegliere Comunicazioni **esterne.**

    Nella pagina **Opzioni** verranno selezionate tutte le opzioni. Deselezionare le comunicazioni da disabilitare. L'immagine seguente mostra che Jakob sarà in grado di comunicare con persone di altre aziende attendibili, ma non con altri utenti Skype.

    ![Scegliere Contatti esterni](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Scegliere **Save**.

> [!NOTE]
> Potrebbe essere necessario attendere fino a 24 ore per l'applicazione delle modifiche.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Argomenti correlati

<a name="bk_preview"> </a>

[Configurare Skype for Business online](set-up-skype-for-business-online.md)
  
[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)
