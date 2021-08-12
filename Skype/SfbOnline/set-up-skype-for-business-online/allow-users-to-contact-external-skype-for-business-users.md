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
description: "Informazioni su come configurare le Skype for Business per consentire agli utenti di parlare con utenti di un'altra organizzazione o per consentire ai contatti esterni di parlare con loro. "
ms.openlocfilehash: 025cb6d430fd4dda2c4b3b7c4d351d9954c97d252456fce73b50df21c5bdf303
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308059"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Permettere agli utenti di contattare utenti Skype for Business esterni

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
  
Seguire la procedura descritta in questo articolo quando:
  
- Si hanno utenti di domini diversi nell'azienda. Ad esempio, Rob@ContosoEast.com e Ann@ContosoWest.com.

- Si vuole che le persone dell'organizzazione usino le Skype for Business per contattare persone di aziende specifiche esterne all'organizzazione.

- Si vuole che chiunque altro al mondo che usa Skype for Business possa trovare e contattare l'utente usando il proprio indirizzo di posta elettronica. Se l'utente e l'utente usano le impostazioni Skype for Business predefinite, questa funzionerà automaticamente. In caso contrario, è necessario assicurarsi che la configurazione non blocchi il dominio.

## <a name="enable-business-to-business-communications-for-your-users"></a>Abilitare le comunicazioni business-to-business per gli utenti

<a name="bk_preview"> </a>

Per eseguire [questa](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) comunicazione, è Microsoft 365 o Office 365 autorizzazioni di amministratore in entrambe le organizzazioni.

![Icona che mostra il logo Microsoft Teams ](../images/teams-logo-30x30.png) **con l'interfaccia Teams di amministrazione**
  
1. Accedere con l'account Microsoft 365 o Office 365 amministratore.

2. Nell'interfaccia di amministrazione passare a **Interfaccia di amministrazione**  >  **Teams**.

    ![Scegliere l'Teams amministratore.](../images/MS-Teams-Admin.png)
  
3. Nel centro **Teams scegliere** **Skype** > **portale legacy** 
  ![ Scegliere il portale legacy SfB.](../images/SFBlegacy-size65.png)

4. Nell'**interfaccia di amministrazione di Skype for Business** scegliere **Organizzazione** > **Comunicazioni esterne**.
5. Per configurare la comunicazione con una specifica azienda o con utenti in un altro dominio, nella casella di riepilogo a discesa scegliere **Attiva solo per i domini consentiti**.

    Oppure, se si vuole abilitare la comunicazione con tutti gli altri utenti del mondo che hanno criteri di Skype for Business, scegliere Attivato ad eccezione **dei domini bloccati.** Questa è l'impostazione predefinita.

6. In **Domini bloccati o consentiti** scegliere e aggiungere il nome del dominio da **+** consentire.

7. Assicurarsi che l'amministratore dell'altra organizzazione eseerciti gli stessi passaggi **nell'interfaccia Skype for Business di amministrazione.** Ad esempio, **nell'elenco dei domini consentiti,** l'amministratore deve immettere il dominio per l'azienda.

8. Se si usa firewall Windows, Skype for Business automaticamente le porte necessarie.

    Se l'organizzazione usa una soluzione firewall diversa per limitare la connessione a Internet dei computer della rete, verificare che i computer client siano in grado di accedere agli URL e agli intervalli di indirizzi [IP](/microsoftteams/office-365-urls-ip-address-ranges)Office 365 seguenti. Potrebbe essere necessario aggiungere gli FQDN all'elenco di indirizzi consentiti in uscita nella configurazione del firewall o dell'infrastruttura proxy: **\* .api.skype.com,** \* *_.users.storage.live.com_* e **graph.skype.com**. Per istruzioni su come aprire queste porte nel firewall, consultare la documentazione fornita con essa.

    Per un elenco di tutte le porte da aprire, vedere Office 365 [URL e intervalli di](/microsoftteams/office-365-urls-ip-address-ranges)indirizzi IP.

9. Assicurarsi che anche l'amministratore dell'organizzazione abbia seguito questa procedura.

10. **ATTENDERE FINO A 24 ORE PER TESTARE**. Quando si modificano le impostazioni delle comunicazioni esterne, possono essere necessarie fino a 24 ore prima che le modifiche possano essere popolate in tutti i data center.

![](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png)Skype È possibile consentire agli utenti di cercare e messaggistica istantanea con tutti gli utenti che Skype, l'app gratuita consumer. Per altre informazioni, vedere [Consentire agli Skype for Business di aggiungere Skype contatti.](let-skype-for-business-users-add-skype-contacts.md)
  
## <a name="test-and-troubleshoot"></a>Testare e risolvere i problemi

<a name="bk_preview"> </a>

 **Il problema più comune che le persone riscontrano quando si configurano le comunicazioni business-to-business è ottenere gli URL Office 365 e gli intervalli di indirizzi [IP.](/microsoftteams/office-365-urls-ip-address-ranges)**
  
Per testare la configurazione, è necessario un contatto Skype for Business che non sia dietro il firewall aziendale.
  
1. Dopo aver modificato le impostazioni delle comunicazioni esterne, **ATTENDERE FINO A 24 ORE PER VERIFICARE**.

2. In Skype for Business, cercare il contatto in Skype for Business e inviare una richiesta di chat.

    Se viene visualizzato un messaggio che indica che non è stato possibile inviare il messaggio a causa dei criteri aziendali, è necessario verificare gli URL e gli intervalli di indirizzi IP Office 365 indirizzi [IP.](/microsoftteams/office-365-urls-ip-address-ranges)

3. Chiedi al tuo Skype for Business contatto di inviarti una richiesta di chat. Se non si riceve la richiesta, il problema sono le impostazioni del firewall, supponendo di aver già verificato che le impostazioni firewall dell'altra organizzazione siano corrette.

4. Un altro modo per verificare se il problema è il firewall è passare a una posizione WiFi non dietro il firewall, ad esempio una caffetteria. Usare Skype for Business per inviare una richiesta al contatto per chattare. Se il messaggio viene inviato, ma non al lavoro, il problema è il firewall.

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Come trovare altri utenti ed essere trovati quando ci si connette con un'altra azienda

<a name="bk_preview"> </a>

Dopo aver abilitato la comunicazione esterna con altri Skype for Business utenti, gli utenti possono trovare utenti Skype for Business federati cercando i nomi di accesso. Un esempio è Rob@contoso.com. Dovrà quindi aggiungere la persona all'elenco dei contatti.
  
![Per trovare un utente in un'azienda federata, è necessario cercarne l'indirizzo di posta elettronica ,in genere anche il nome di accesso.](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Suggerimenti sulla configurazione delle comunicazioni con le aziende federate

<a name="bk_preview"> </a>

- Per configurare la federazione tra Skype for Business 2015 e Skype for Business Online, vedere questo articolo: Configurare la federazione [con Skype for Business Online.](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)

- Per configurare la federazione tra Lync e Skype for Business Online, vedere questo articolo: Configurazione del supporto della federazione [per un cliente di Lync Online.](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)

- Quando due utenti di Skype for Business in Microsoft 365 o Office 365 comunicano tra loro in domini separati, possono usare solo le funzionalità di Skype for Business ,ad esempio le conversazioni video o la condivisione desktop, attivate in entrambe le organizzazioni.

- Se un utente Skype for Business dell'organizzazione viene abilitato a un blocco In-Place o per controversia legale, tutte le conversazioni istantanee tra tale utente e altri utenti di Skype for Business o Skype verranno salvate **in** Elementi ripristinabili nella propria cassetta postale. Queste conversazioni non vengono salvate nella cartella **Cronologia** conversazioni della cassetta postale.

## <a name="turn-off-external-communication-for-specific-individuals"></a>Disattivare le comunicazioni esterne per utenti specifici

<a name="bk_preview"> </a>

Dopo aver abilitato la comunicazione esterna per l'intera azienda, è possibile disattivarla solo per utenti specifici.
  
1. Accedere con l'account Microsoft 365 o Office 365 amministratore.

2. Nell'interfaccia di amministrazione passare a **Utenti**  >  **utenti attivi**.

3. Nell'elenco degli utenti scegliere l'utente e quindi, in Altre Impostazioni **,** fare clic su Modifica Skype for Business **proprietà**.

    ![Scegliere Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. **Nell'Skype for Business di amministrazione scegliere** Comunicazioni **esterne.**

    Nella pagina **Opzioni** verranno selezionate tutte le opzioni. Deselezionare le comunicazioni da disabilitare. L'immagine seguente mostra che Jakob sarà in grado di comunicare con persone di altre aziende attendibili, ma non con altri Skype utenti.

    ![Scegliere Contatti esterni](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Scegliere **Save**.

> [!NOTE]
> Potrebbe essere necessario attendere fino a 24 ore per l'applicazione delle modifiche.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Argomenti correlati

<a name="bk_preview"> </a>

[Configurare Skype for Business online](set-up-skype-for-business-online.md)
  
[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)
