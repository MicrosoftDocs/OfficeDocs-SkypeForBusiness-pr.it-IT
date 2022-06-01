---
title: Connessione Microsoft Teams Essentials (identità AAD) a un sistema di posta elettronica esistente con calendario
author: adjoseph
ms.author: adjoseph
ms.reviewer: jimmyw
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Informazioni su come connettere Microsoft Teams Essentials (identità AAD) a un sistema di posta elettronica esistente con calendario come Google Workspace
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dcea261be727c01382d55c4a2861541291fcb343
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823587"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>Connessione Microsoft Teams Essentials (identità AAD) a un sistema di posta elettronica esistente con calendario

Questa guida fornisce i passaggi di configurazione per connettere Microsoft Teams Essentials (identità AAD) a un sistema di posta elettronica esistente con calendario.

Microsoft Teams Essentials (identità AAD) riunisce il meglio di Teams con riunioni, chat, chiamate e collaborazione. Teams Essentials (identità AAD) può connettersi al sistema di posta elettronica esistente per offrire un'esperienza integrata, ad esempio avere tutte le notifiche di Teams in una cartella Posta in arrivo esistente, tutti gli eventi del calendario in Teams e la possibilità di accedere a Teams con l'indirizzo di posta elettronica esistente.

Una volta effettuata la connessione, è possibile visualizzare le risposte alle riunioni pianificate e gli inviti alla collaborazione nella cassetta postale e nella Microsoft Teams. È anche possibile visualizzare e interagire con le riunioni in arrivo dal calendario usando Teams e software per riunioni di terze parti come Google Workspace.

## <a name="prerequisites"></a>Prerequisiti

I passaggi di configurazione descritti in questo articolo prevedono l'inoltro automatico di elementi da Exchange Online. Per impostazione predefinita, l'inoltro automatico è disabilitato dai criteri in uscita per la posta indesiderata. Questo criterio deve essere abilitato per connettere Teams Essentials a una cassetta postale e a un sistema di calendario esistenti.

Per abilitare l'inoltro automatico:

1. Vai al portale di Microsoft 365 Defender all'indirizzo<https://security.microsoft.com/>
2. Nel menu di spostamento a sinistra passare a **Criteri di posta elettronica & collaborazione** > **& regole** > **Minacce** > **nella sezione** Criteri
3. Nella pagina **Criteri di protezione dalla posta indesiderata** selezionare **Criteri in uscita per la posta indesiderata (impostazione predefinita)** nell'elenco
4. Nel riquadro a comparsa dei dettagli dei criteri visualizzato selezionare **Modifica impostazioni di protezione** per modificare la regola di scorrimento automatico.
5. In **Regole di inoltro** impostare la condizione di inoltro automatico **su Attivato: l'inoltro è abilitato** e salvare le modifiche.

:::image type="content" source="media/essentials-antispam.png" alt-text="Immagine che mostra il riquadro a comparsa dei criteri in uscita per la posta indesiderata di Microsoft Defender Portal con la condizione Attivato, l'inoltro è abilitato in Regole di inoltro." :::

Per altre informazioni sulla configurazione dei criteri di posta indesiderata in uscita, vedere [Configurare il filtro della posta indesiderata in uscita - Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true).

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>Connessione Teams Essentials per Exchange Online con Exchange locale

È possibile sfruttare tutte le caratteristiche offerte da Teams Essentials (AAD) usando un approccio ibrido per configurare la connessione tra Microsoft Teams e Exchange Online con Exchange locale.

Per fare in modo che l'accesso al calendario funzioni per le cassette postali locali, seguire le istruzioni fornite in[Configurazione dell'accesso Teams calendario per Exchange cassette postali locali - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)

Per distribuire Microsoft Teams Rooms in un ambiente ibrido con Exchange locale, visitare [la pagina Distribuire Microsoft Teams Rooms con Exchange locale - Microsoft Teams | Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>Connessione Teams Essentials a sistemi di posta elettronica di terze parti con calendario

Se non si prevede di trasferire la cassetta postale dell'organizzazione in Microsoft 365, è possibile connettere Teams Essentials a un sistema di posta elettronica e calendario di terze parti esistente. Questa connessione consente di ricevere notifiche Teams nel sistema di posta elettronica esistente durante la visualizzazione di inviti alle riunioni ed eventi del calendario esistenti in Microsoft Teams.

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>Connessione Teams Essentials alla posta elettronica di terze parti usando il dominio vanity (esempio google workspace)

La sezione seguente illustra come connettere Microsoft Teams a un sistema di posta elettronica esistente con il calendario, come Google Workspace. Per eseguire questa connessione, lasciare intatto il sistema di posta elettronica corrente, inoltrare tutti i messaggi a Exchange Online, filtrare tutto tranne i messaggi di posta elettronica del tipo di calendario. In questo modo, i messaggi di posta elettronica in calendario vengono visualizzati automaticamente nel Teams calendario accettato come provvisorio e i messaggi di tipo non di calendario vengono eliminati.

Tutta la posta elettronica generata in Microsoft 365 viene inoltrata a Google Workspace in modo che gli utenti possano ricevere promemoria e notifiche Teams. Le identità utente, come l'indirizzo di posta elettronica principale dell'utente, possono essere duplicate. Single Sign-On è anche possibile, ma non obbligatorio. Gli utenti devono poter partecipare a Teams riunioni dal calendario di terze parti o Teams calendario. Un'altra funzionalità Teams funzionerà come previsto.

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="Immagine che illustra un diagramma del flusso di posta tra EXO e Gmail":::

Questi esempi si basano sul cmdlet di PowerShell [di Connessione-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline) che fa parte del [modulo Exchange Online PowerShell V2](/powershell/exchange/exchange-online-powershell-v2?preserve-view=true&view=exchange-ps). Se viene visualizzato un messaggio di errore durante l'esecuzione di Connessione-ExchangeOnline, assicurarsi di aver seguito le istruzioni consigliate per l'installazione del modulo usando [Installa il modulo EXO V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-EXO-v2-module). Quando Connect-ExchangeOnline richiede le credenziali, assicurarsi di usare un account di amministratore tenant.

#### <a name="step-one-set-up-a-new-microsoft-365-tenant-domain"></a>Passaggio 1: Configurare un nuovo dominio tenant di Microsoft 365

1. Passare all'interfaccia di amministrazione in <https://admin.microsoft.com>.

2. Passare a **Configurazione** > **domini**  e selezionare **Aggiungi dominio** per aggiungere il dominio esistente. Se non si aggiunge un dominio, gli utenti dell'organizzazione useranno il dominio onmicrosoft.com per i propri indirizzi di posta elettronica fino a quando non viene aggiunto. Assicurarsi di aggiungere il dominio prima di aggiungere utenti, in modo da non dover configurarli due volte.

3. Verificare il dominio con un record TXT seguendo la procedura descritta in [Verificare con un record TXT](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true).

4. Quando richiesto, selezionare **Non consentire a Microsoft 365 di configurare IL DNS**.

5. Quando richiesto, lasciare attivi i record MX esistenti senza modificarli.

6. Aggiornare il record TXT SPF esistente per includere Microsoft 365.

7. Configurare DomainKeys Identified Mail (DKIM) per Microsoft 365 eseguendo questa procedura per [configurare manualmente DKIM](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true).

8. Accedi nuovamente al interfaccia di amministrazione di Microsoft 365 per <https://admin.microsoft.com/AdminPortal/> abilitare DKIM

9. Nel riquadro di spostamento a sinistra selezionare **Setup** > **Domains**

10. Usando la casella di controllo, selezionare il dominio non Microsoft esistente, ad esempio TomislavK@thephone-company.com, dagli elenchi di domini correnti.

11. Seleziona il pulsante con **tre punti verticali** per aprire un menu.

12. Nel menu seleziona **Imposta come predefinito**

13. **Conferma imposta come predefinito** nella finestra che viene visualizzata per impostare il dominio esistente come predefinito.
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Immagine della finestra di dialogo di conferma per l'impostazione del dominio come predefinito":::

    Per altre indicazioni sull'aggiunta di un dominio a Microsoft 365, seguire i passaggi descritti in [Aggiungere un dominio a Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).

#### <a name="step-two-add-users-and-assign-teams-essentials-licenses"></a>Passaggio 2: Aggiungere utenti e assegnare licenze di Teams Essentials

1. Passare all'interfaccia di amministrazione in <https://admin.microsoft.com> per aggiungere un singolo utente

2. Passare a **Utenti** > **attivi** e selezionare **Aggiungi un utente**

3. Nel riquadro **Configura le nozioni di base** immettere le informazioni di base sull'utente, quindi selezionare **Avanti**.
    - **Nome:** Immettere il nome e il cognome, il nome visualizzato e il nome utente.
    - **Dominio:** Scegliere il dominio per l'account dell'utente. Ad esempio, se il nome utente è Pio e il dominio è contoso.com, eseguirà l'accesso usando jakob@contoso.com.
    - **Impostazioni password:** Scegliere di usare la password generata automaticamente o di creare una password complessa personalizzata per l'utente.  Determinare se si vuole inviare la password in un messaggio di posta elettronica quando l'utente viene aggiunto.

4. Nel riquadro **Assegna licenze di prodotto** selezionare la posizione e la licenza appropriata per l'utente. Se non sono disponibili licenze, è comunque possibile aggiungere un utente e acquistare altre licenze. Selezionare Avanti.

5. Nel **riquadro Impostazioni facoltative** espandere **Ruoli** per impostare l'utente come amministratore. Espandere **Le informazioni del profilo** per aggiungere altre informazioni sull'utente.

6. Seleziona **Avanti**, rivedi le impostazioni del nuovo utente, apporta eventuali altre modifiche, quindi seleziona **Completa aggiunta**, quindi chiudi.

Per aggiungere più utenti contemporaneamente, seguire la procedura consigliata in [Aggiungere utenti e assegnare licenze - Microsoft 365 amministratore | Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

#### <a name="step-three-configure-google-workspace"></a>Passaggio tre: Configurare Google Workspace

***Configurare il doppio recapito della posta elettronica per Microsoft 365 e rimuovere allegati:***

1. Segui i passaggi di Google per configurare la doppia consegna: <https://support.google.com/a/answer/9228551?hl=en>

2. Aggiungere il percorso per Office 365

    - Vai alla console di Google Amministrazione all'indirizzo <https://admin.google.com>)
    - Passare a App > Google Workspace > host > Gmail.
    - Immettere un nome per l'itinerario. (Ad esempio, Microsoft 365)
    - Scegliere "Host singolo" e immettere il record MX specificato per dominio in Microsoft 365 (ad esempio: ContosoLandscaping2-m365master-com.mail.protection.outlook.com)

    **Metodo smart host per risolvere il codice di risposta ATTR35 quando la posta viene inviata a Exchange locale/Exchange Online:**
    - Scegliere "Host singolo" e immettere il record MX per il dominio iniziale del tenant come smart host. Il dominio iniziale è nel formato GUID.onmicrosoft.com. Un GUID è un valore univoco fornito a ogni organizzazione nell'ambito della registrazione al servizio. Un GUID è un numero intero a 128 bit (16 byte) che può essere usato in tutti i computer e le reti in cui è richiesto un identificatore univoco.
    - È possibile usare la riga di comando: nslookup -type MX GUID.onmicrosoft.com per risolvere il record MX (ad esempio: contosolandscaping2.mail.protection.outlook.com)
    - Scegliere **Porta:25**
    - Procedere con le opzioni consigliate

3. Configurare il percorso per Office 365

    - Aprire la **console di Google Amministrazione** all'indirizzo<https://admin.google.com>

    - Passare a **Routing** **Gmail** > **di Google Workspace** >  per **le app** > 

    - Nella scheda **Routing** seleziona **Configura**

    - Immettere **Nome** per la regola. Ad esempio, Gmail da Office 365)

    - Per **fare in modo che i messaggi di posta elettronica abbiano effetto**, selezionare Sia **In ingresso** che  **Ricezione interna**

    - In **Per i tipi di messaggi precedenti**, selezionare **Modifica messaggio**

    - In **Recapita anche a** selezionare **Aggiungi altri destinatari** , quindi selezionare **Aggiungi per aggiungere il percorso di posta secondario.**

    - In **Destinatari** selezionare la freccia in giù "" e selezionare **Avanzate.**

    - Selezionare **Cambia itinerario.**

    - Nell'elenco selezionare il percorso di posta secondario creato in precedenza

    - In **Allegati** selezionare **Rimuovi allegati dal messaggio**

    - Scorri verso il basso e seleziona **Salva**.

***Aggiungere il sottodominio in Google Workspace per ricevere posta elettronica da Microsoft 365.***

  Creare quindi regole di inoltro in Microsoft 365 cassette postali nel sottodominio. Scegliere un sottodominio da usare in Google Workspace per ricevere posta elettronica da Microsoft 365 (ad esempio, g.contosolandscaping2.m365master.com)

1. Inizia dalla **console di Google Amministrazione** (all admin.google.com)

2. Passare a **Account** > **Domains** > **Manage Domains**

3. Selezionare **Aggiungi dominio**

4. Immettere il nome di dominio selezionato

5. Selezionare **il dominio alias utente**

6. Selezionare **Aggiungi dominio & avviare la verifica**

7. Attendere il completamento della verifica e aggiornare la pagina

8. Selezionare **Attiva Gmail**

9. Scegliere **Ignora configurazione record MX** e quindi selezionare **AVANTI**

10. Nella finestra di dialogo **Instrada la posta a un altro server** prendere nota del server a cui instradare la posta (ad esempio, aspmx.l.google.com) e selezionare **Uso un altro server della posta**

***Consentire ai messaggi di posta elettronica provenienti da Microsoft 365 di ignorare il filtro della posta indesiderata***

1. Trovare un'intestazione appropriata dal tenant Microsoft 365 inviando un messaggio di posta elettronica a un utente nell'area di lavoro di Google.

2. Aprire il messaggio e selezionare **Mostra originale**

3. Scegliere un'intestazione di posta elettronica che identifichi in modo univoco i messaggi provenienti dal tenant di Microsoft 365. Ad esempio, X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

4. Vai alla **console di Google Amministrazione** all'indirizzo<https://admin.google.com>

5. Passare a **Conformità** **gmail** >  di **Google Workspace** >  per **le app** > 

6. Passare a **Conformità contenuto** e selezionare **Configura**

7. Assegnare un nome all'impostazione. Ad esempio, Allowlist Microsoft 365 posta elettronica.

8. In **Messaggi di posta elettronica che influiscono sull'archiviazione** in ingresso

9. In **Aggiungi espressioni che descrivono il contenuto da cercare in ogni messaggio** selezionare **se una delle seguenti corrispondenze al messaggio**

10. In **Espressioni** selezionare **Aggiungi** xi. In **Aggiungi,** scegliere **Corrispondenza contenuto avanzata**

11. In **Posizione** scegliere **Intestazioni complete**

12. In **Tipo corrispondenza** scegliere **Testo completo**

13. In Contenuto immettere l'intestazione di posta elettronica che identifica in modo univoco i messaggi provenienti dal tenant di Microsoft 365 ,ad esempio X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

14. Seleziona **Salva**

15. In **Se le espressioni precedenti corrispondono, eseguire il campo seguente** > **Modifica messaggio** e selezionare **Ignora filtro posta indesiderata per questo messaggio** in **Posta indesiderata**.

16. Seleziona **Salva**

#### <a name="step-four-configure-microsoft-365-settings-for-the-integration"></a>Passaggio quattro: Configurare le impostazioni di Microsoft 365 per l'integrazione

*Configurare il connettore per instradare la posta da Microsoft 365 a Gmail:*

1. Vai al **Centro Amministrazione Microsoft** all'indirizzo<https://admin.microsoft.com/AdminPortal>

2. Seleziona **Mostra tutto** nel menu di spostamento a sinistra.

3. In **Centri Amministrazione** selezionare **Exchange** per aprire l'interfaccia di amministrazione di Exchange in una nuova scheda

4. Nel menu di spostamento sinistro **dell'interfaccia** di amministrazione di Exchange selezionare **Connettori flusso** >  di posta, aprire il menu di overflow (...) e selezionare Aggiungi connettore

5. In **Connessione da** nella nuova finestra del connettore selezionare **Office 365**

6. In **Connessione per** selezionare il server di posta elettronica dell'organizzazione, quindi selezionare **Avanti**

7. Immetti un **nome** per il nuovo connettore (ad esempio, In Gmail) e continua **Avanti**

8. Nella sezione **Uso del connettore** selezionare **Solo quando è configurata una regola di trasporto che reindirizza i messaggi a questo connettore** e selezionare **Avanti**.

9. Nella sezione Routing immettere lo smart mail host appropriato (ad esempio, aspmx.l.google.com), selezionare **+** e continuare **con Avanti**.

10. Nella sezione **Restrizioni di sicurezza** accettare le impostazioni predefinite selezionando **Avanti**

11. Nella **sezione Messaggio di posta elettronica di convalida** immettere un indirizzo di posta elettronica valido per il sistema Gmail (ad esempio johannal@g.contosolandscaping2.m365master.com), selezionare il **segno più (+)** e quindi selezionare **Convalida**

12. Attendere il completamento della convalida e, se la convalida ha esito positivo, premere Avanti

13. In **Rivedi connettore** verificare che la configurazione sia corretta e premere Crea connettore

14. Quando viene visualizzata la notifica Connettore creato, premere **Fine**

*Inoltrare la posta da Microsoft 365 cassette postali a Gmail:*

1. Usare Amministrazione Microsoft 365 **Center** per aggiornare ogni cassetta postale oppure è possibile usare uno script di **PowerShell**, ad esempio:

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {

    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    }
    ```

    **Risoluzione dei problemi Connessione-ExchangeOnline:**

    Si verifica un errore durante l'esecuzione di Connessione-ExchangeOnline? Questo potrebbe essere il risultato della regola di inoltro automatico della posta elettronica dell'organizzazione. Per impostazione predefinita, l'inoltro automatico è disabilitato. Per connettere Teams Essentials a Google Workspace, la regola deve essere abilitata.

    Immettere lo script seguente:

   ```powershell
    Set-ExecutionPolicy Unrestricted
     ```

    In seguito, eseguire i comandi seguenti:

    ```powershell
    Enable-OrganizationCustomization
    Get-HostOutboundSpamFilterPolicy | set-HostedOutboundSpamFilterPolicy -AutoForwardingMode On
    ```

*Configurare Exchange Online regola di trasporto diretta al calendario:*

1. La configurazione di questa impostazione accetta automaticamente gli inviti al calendario in modo che vengano visualizzati in Teams calendario senza che gli utenti interagiscano con l'invito in Outlook Web App.

2. Per creare le regole di trasporto, è possibile usare lo script seguente:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems

    ```

*Disabilitare Outlook sul web per le cassette postali:*

1. Seguire le istruzioni in [Abilitare o disabilitare Outlook sul web per una cassetta postale in Exchange Online](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app) per disabilitare Outlook sul web per le cassette postali.

2. È possibile disabilitare Outlook sul web usando il **Centro Exchange Amministrazione** o **PowerShell**. È possibile usare l'esempio di PowerShell seguente per disabilitare Outlook sul web per tutte le cassette postali:

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

#### <a name="step-five-configure-exchange-online-domain-for-internal-relay"></a>Passaggio 5: Configurare Exchange Online dominio per l'inoltro interno

Questo passaggio assicura che la posta elettronica venga inviata a un sistema di terze parti per la risoluzione finale.

1. Vai al **Centro Amministrazione Microsoft** all'indirizzo<https://admin.microsoft.com/AdminPortal>

2. Nel riquadro di spostamento sinistro seleziona **Mostra tutto**

3. In **Centri Amministrazione** seleziona **Exchange** per aprire Exchange interfaccia di amministrazione in una nuova scheda

4. Nell **Exchange afaccia di amministrazione** selezionare **Flusso di posta** dal menu di spostamento a sinistra, quindi selezionare **Domini accettati**

5. Toccare il nome di dominio configurato nel sistema di terze parti, ad esempio contosoLandscaping2.m365master.com

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="Immagine che mostra le impostazioni dell Exchange interfaccia di amministrazione per il flusso di posta.":::

6. Selezionare **Inoltro interno**, quindi fare clic su **Salva**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Immagine che mostra l'azione di salvataggio dell'impostazione di inoltro interno.":::

#### <a name="step-six-create-a-rule-to-delete-all-inbound-mail-to-exchange-online-except-for-calendaring"></a>Passaggio sei: Creare una regola per eliminare tutta la posta in ingresso da Exchange Online ad eccezione del calendario

1. È possibile configurare questa regola nel **Centro Exchange Amministrazione** o **in PowerShell**. È possibile usare l'esempio di **PowerShell** seguente per creare la regola:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>Connessione Teams Essentials alla posta elettronica di terze parti che non usa il dominio vanity (esempio Gmail)

È possibile pianificare e partecipare a una riunione Teams direttamente da Google Workspace collegando un account Gmail consumer a Teams Essentials, facendo affidamento principalmente [sull'aggiunta di Teams G Suite](https://support.microsoft.com/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60). In questo modo è possibile pianificare video e audioconferenze con condivisione dello schermo, chat delle riunioni, lavagne digitali e altro ancora.

Si configurerà Gmail in modo da estrarre la posta elettronica da Exchange Online per assicurarsi che i messaggi generati in Microsoft 365 e Teams arrivino correttamente in Gmail. Potrebbe essere necessario disabilitare le impostazioni predefinite di sicurezza per eseguire questa connessione, il che rende essenziale l'uso di una password univoca complessa. Un dominio personalizzato non è necessario per questo scenario, ma può essere configurato in Microsoft 365 per l'uso in Gmail, se si vuole usarne uno.

:::image type="content" source="media/essentials-gmail.png" alt-text="Immagine che descrive il flusso di posta tra Teams Essentials e Gmail":::

#### <a name="1-ensure-that-you-have-a-gmail-account-set-up"></a>1. Verificare che sia configurato un account Gmail

Se si ha già un account esistente, è possibile procedere con il passaggio successivo. In caso contrario, vedere [Creare un nuovo account Google](https://accounts.google.com/SignUp?hl=en) per configurare un nuovo account Gmail.

#### <a name="2-set-up-your-microsoft-365-tenant"></a>2. Configurare il tenant di Microsoft 365

*Configurare Teams utenti AAD:*

1. Seguire le istruzioni in[Aggiungere utenti e assegnare licenze](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) per aggiungere più utenti

*Configurare la protezione delle identità:*

1. Disabilita le impostazioni predefinite di sicurezza, se attive.

2. Configurare l'autenticazione a più fattori per gli utenti

3. Se si usa l'accesso condizionale, assicurarsi di fare eccezione per l'accesso POP alla cassetta postale

*Aggiungi dominio al Centro Amministrazione Microsoft 365 (facoltativo):*

1. In Spostamento selezionare Impostazioni > Dominio, quindi selezionare Aggiungi dominio

2. Immettere il nome di dominio nel campo appropriato

3. Seguire le istruzioni visualizzate per verificare il dominio con il record TXT

4. Quando richiesto, consentire a Microsoft di configurare il DNS

5. Completare le istruzioni per verificare il percorso dei record MX per Microsoft 365

6. Configurare il record TXT SPF per includere Microsoft 365

7. Completare le istruzioni per la configurazione dei record TXT DKIM per Microsoft 365

8. Verifica che DKIM sia abilitato disconnettendosi e accedendo di nuovo al centro Amministrazione

#### <a name="3-configure-gmail"></a>3. Configurare Gmail

1. Configurare Gmail per il pull di Exchange Online posta nel sistema

2. Configurare il componente aggiuntivo Calendario Teams

3. Abilitare Gmail per l'uso del dominio aziendale (facoltativo)
