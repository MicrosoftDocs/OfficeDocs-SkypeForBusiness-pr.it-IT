---
title: Connessione Microsoft Teams Essentials (AAD Identity) a un sistema di posta elettronica esistente con calendario
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
description: Informazioni su come connettersi Microsoft Teams Essentials (AAD Identity) a un sistema di posta elettronica esistente con un calendario come Google Workspace
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d113446971375ace51335a6654c8599f8d2c35b
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257528"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>Connessione Microsoft Teams Essentials (AAD Identity) a un sistema di posta elettronica esistente con calendario

Questa guida fornisce i passaggi di configurazione per connettere Microsoft Teams Essentials (AAD Identity) a un sistema di posta elettronica esistente con il calendario.

Microsoft Teams Essentials (AAD Identity) riunisce il meglio Teams riunioni, chat, chiamate e collaborazione. Teams Essentials (AAD Identity) può connettersi al sistema di posta elettronica esistente per offrire un'esperienza integrata, come la presenza di tutte le notifiche di Teams in una posta in arrivo esistente, tutti gli eventi del calendario in Teams e la possibilità di accedere a Teams con l'indirizzo di posta elettronica esistente.

Dopo la connessione, è possibile visualizzare le risposte alle riunioni pianificate e gli inviti a collaborare nella cassetta postale e Microsoft Teams. È anche possibile visualizzare e interagire con le riunioni in arrivo dal calendario usando Teams e software per le riunioni di terze parti come Google Workspace.

## <a name="prerequisites"></a>Prerequisiti

I passaggi di configurazione descritti in questo articolo implicano il processo di inoltro automatico degli elementi Exchange Online. Per impostazione predefinita, l'inoltro automatico è disabilitato dai criteri di posta indesiderata in uscita. Questo criterio deve essere abilitato per connettersi Teams Essentials a un sistema di cassette postali e calendario esistente.

Per abilitare l'inoltro automatico:

1. Passare al portale di Microsoft 365 Defender all'indirizzo<https://security.microsoft.com/>
2. Nel menu di spostamento sinistro passare a Criteri di collaborazione & di posta elettronica & criteri di protezione dalla posta indesiderata  >    >    >   nella sezione Criteri
3. Nella pagina **Criteri di protezione** da posta indesiderata selezionare Criterio posta indesiderata in uscita **(impostazione predefinita)** nell'elenco
4. Nel riquadro a comparsa dei dettagli dei criteri visualizzato selezionare Modifica impostazioni **di protezione** per modificare la regola di protezione automatica.
5. In **Regole di inoltro** impostare la condizione di inoltro automatico su **Attivato:** l'inoltro è abilitato e salvare le modifiche.

:::image type="content" source="media/essentials-antispam.png" alt-text="Immagine che mostra il riquadro a comparsa dei criteri in uscita antispam di Microsoft Defender Portal con attivato, l'inoltro è abilitato in Regole di inoltro." :::

Per altre informazioni sulla configurazione dei criteri di posta indesiderata in uscita, vedere Configurare il filtro della posta indesiderata in uscita [- Office 365 | Documenti Microsoft](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true).

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>Connessione Teams Essentials per Exchange Online con Exchange locale

È possibile usufruire di tutto ciò che Teams Essentials (AAD) offre usando un approccio ibrido per configurare la connessione tra Microsoft Teams e Exchange Online con Exchange locale.

Per far funzionare l'accesso al calendario per le cassette postali locali, seguire le istruzioni fornite in Configurazione dell'accesso al calendario di Teams per le cassette postali locali di[Exchange - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)

Per distribuire Microsoft Teams Rooms in un ambiente ibrido con Exchange locale, vedere Distribuire Microsoft Teams Rooms con Exchange locale [- Microsoft Teams | Documenti Microsoft](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>Connessione Teams Essentials a sistemi di posta elettronica di terze parti con calendario

Se non si prevede di cambiare la cassetta postale dell'organizzazione in Microsoft 365, è possibile connettere Teams Essentials a un sistema di posta elettronica e calendario di terze parti esistente. Questa connessione consente di ricevere Teams notifiche nel sistema di posta elettronica esistente durante la visualizzazione di inviti a riunioni ed eventi del calendario esistenti in Microsoft Teams.

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>Connessione Teams essentials alla posta elettronica di terze parti con vanity domain (esempio di Google Workspace)

La sezione seguente illustra come connettersi Microsoft Teams un sistema di posta elettronica esistente con il calendario, ad esempio Google Workspace. Questa connessione verrà eseguita lasciando intatto il sistema di posta elettronica corrente, inoltrando tutti i messaggi di posta elettronica a Exchange Online, filtrando tutto tranne i messaggi di posta elettronica di tipo calendario. In questo modo, i messaggi di posta elettronica del calendario vengono visualizzati automaticamente nel calendario Teams vengono eliminati come messaggi di posta elettronica provvisori e non di tipo calendario.

Tutti i messaggi generati in Microsoft 365 vengono inoltrati a Google Workspace in modo che gli utenti Teams promemoria e notifiche. Le identità degli utenti, come la posta elettronica principale dell'utente, possono essere duplicate. Single Sign-On è anche possibile, ma non obbligatorio. Gli utenti devono essere in grado di partecipare Teams riunioni dal calendario di terze parti o dal Teams calendario. Altre Teams funzionalità funzionano come previsto.

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="Immagine che illustra un diagramma del flusso di posta tra EXO e Gmail":::

Questi esempi si basano Connessione commandlet di [PowerShell](/powershell/module/exchange/connect-exchangeonline?view=exchange-ps&preserve-view=true) di ExchangeOnline che fa parte del modulo [Exchange Online PowerShell V2.](/powershell/exchange/exchange-online-powershell-v2&preserve-view=true) Se viene visualizzato un messaggio di errore durante l'esecuzione di Connessione-ExchangeOnline, assicurarsi di aver seguito le istruzioni consigliate per l'installazione del modulo usando Installa il modulo [EXO V2.](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps&preserve-view=true) Quando Connect-ExchangeOnline le credenziali, assicurarsi di usare un account di amministratore tenant.

**Passaggio 1: Configurare un nuovo Microsoft 365 tenant**

1. Passare all'interfaccia di amministrazione in <https://admin.microsoft.com> .

2. Passare a **Configura**  >  **domini e** selezionare Aggiungi **dominio** per aggiungere il dominio esistente. Se non si aggiunge un dominio, gli utenti dell'organizzazione useranno il dominio onmicrosoft.com per gli indirizzi di posta elettronica finché non si fa. Assicurarsi di aggiungere il dominio prima di aggiungere utenti, in modo da non doverli configurare due volte.

3. Verificare il dominio con un record TXT seguendo la procedura descritta in [Verificare con un record TXT](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true).

4. Quando richiesto, selezionare **Non consentire Microsoft 365 configurare DNS**.

5. Quando richiesto, lasciare in posizione i record MX esistenti senza alterarli.

6. Aggiornare il record TXT SPF esistente in modo da includere Microsoft 365.

7. Configurare domainKeys Identified Mail (DKIM) per Microsoft 365 seguendo questa procedura per [configurare manualmente DKIM.](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true)

8. Accedere di nuovo al interfaccia di amministrazione di Microsoft 365 <https://admin.microsoft.com/AdminPortal/> per abilitare DKIM

9. Nel riquadro di spostamento a sinistra selezionare **Configura**  >  **domini**

10. Usando la casella di controllo, selezionare il dominio non Microsoft esistente (ad esempio: JohannaL@contosolandscapting2.m365master.com) dagli elenchi di domini correnti.

11. Selezionare il pulsante con **tre puntini verticali** per aprire un menu.

12. Nel menu seleziona **Imposta come predefinito**

13. **Confermare l'impostazione predefinita** nella finestra che viene visualizzata per impostare il dominio esistente come predefinito.
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Immagine della finestra di dialogo di conferma per l'impostazione predefinita del dominio":::

    Per altre indicazioni sull'aggiunta di un dominio a Microsoft 365, seguire la procedura descritta in Aggiungere un dominio [a Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).

**Passaggio 2: Aggiungere utenti e assegnare Teams licenze di Essentials**

1. Passare all'interfaccia di amministrazione in <https://admin.microsoft.com> per aggiungere un singolo utente

2. Passare a **Utenti**  >  **utenti attivi** e selezionare Aggiungi **utente**

3. Nel riquadro **Configurare le nozioni di** base immettere le informazioni di base sull'utente e quindi selezionare **Avanti.**
    - **Nome:** Immettere il nome e il cognome, il nome visualizzato e il nome utente.
    - **Dominio:** Scegliere il dominio per l'account dell'utente. Ad esempio, se il nome utente dell'utente è Jakob e il dominio è contoso.com, accederà usando jakob@contoso.com.
    - **Impostazioni password:** Scegliere di usare la password rigenerata automaticamente o di creare una password complessa per l'utente.  Determinare se si vuole inviare la password in un messaggio di posta elettronica quando l'utente viene aggiunto.

4. Nel riquadro **Assegna licenze di** prodotto selezionare la posizione e la licenza appropriata per l'utente. Se non si hanno licenze disponibili, è comunque possibile aggiungere un utente e acquistare altre licenze. Selezionare Avanti.

5. Nel riquadro **Impostazioni facoltative** espandere **Ruoli** se si vuole impostare l'utente come amministratore. Espandere **Informazioni profilo** per aggiungere altre informazioni sull'utente.

6. Selezionare **Avanti**, rivedere le impostazioni del nuovo utente, apportare eventuali altre modifiche, se necessario, quindi selezionare **Fine** aggiunta , quindi chiudi.

Per aggiungere più utenti contemporaneamente, seguire la procedura consigliata in Aggiungere utenti e assegnare licenze - Microsoft 365 [amministratore | Documenti Microsoft](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

**Passaggio 3: Configurare Google Workspace**

***Configurare il doppio recapito della posta elettronica Microsoft 365 e rimuovere gli allegati:***

1. Seguire i passaggi di Google per configurare la doppia distribuzione: <https://support.google.com/a/answer/9228551?hl=en>

2. Aggiungere un percorso per Office 365

    - Passare alla Console di amministrazione di Google <https://admin.google.com> all'indirizzo )
    - Passare a App > Google Workspace > gmail > host.
    - Immettere un nome di percorso. Ad esempio, Microsoft 365)
    - Scegliere "Host singolo" e immettere il record MX specificato per il dominio in Microsoft 365 (ad esempio: ContosoLandscaping2-m365master-com.mail.protection.outlook.com)

    **Metodo Smart Host per risolvere il codice di risposta ATTR35 quando la posta viene inviata Exchange locale/Exchange Online:**
    - Scegliere "Host singolo" e immettere il record MX per il dominio iniziale del tenant come smart host. Il dominio iniziale è nel formato GUID.onmicrosoft.com. Un GUID è un valore univoco fornito a ogni organizzazione nell'ambito della registrazione al servizio. Un GUID è un numero intero a 128 bit (16 byte) che può essere usato in tutti i computer e le reti, ovunque sia necessario un identificatore univoco.
    - È possibile usare la riga di comando: nslookup -type MX GUID.onmicrosoft.com per risolvere il record MX (ad esempio: contosolandscaping2.mail.protection.outlook.com)
    - Scegliere **Porta:25**
    - Procedere con le opzioni consigliate

3. Configurare la route per Office 365

    - Aprire la **Console di amministrazione di Google** all'indirizzo <https://admin.google.com>

    - Passare a **App**  >  **Google Workspace**  >  **Gmail**  >  **Routing**

    - Nella scheda **Routing** selezionare **Configura**

    - Immettere **Nome per** la regola. (Ad esempio, Gmail per Office 365)

    - Per **fare in modo che i messaggi di posta** elettronica influiscano su , selezionare sia Ricezione in **ingresso** che  **Ricezione interna**

    - In **Per i tipi di messaggi indicati** sopra, selezionare Modifica **messaggio**

    - In **Recapita anche a** selezionare Aggiungi altri **destinatari,** quindi **selezionare Aggiungi per aggiungere il percorso di posta secondario.**

    - In **Destinatari** selezionare la freccia in giù "" e selezionare **Avanzate.**

    - Selezionare **Cambia percorso.**

    - Nell'elenco selezionare il percorso di posta secondario creato in precedenza

    - In **Allegati** selezionare **Rimuovi allegati dal messaggio**

    - Scorrere verso il basso e selezionare **Salva**.

***Aggiungere il sottodominio nell'area di lavoro di Google per ricevere posta elettronica Microsoft 365.***

  Verranno quindi create regole di inoltro per Microsoft 365 cassette postali al sottodominio. Scegliere un sottodominio da usare in Google Workspace per ricevere posta elettronica da Microsoft 365 (ad esempio, g.contosolandscaping2.m365master.com)

1. Iniziare dalla **Console di amministrazione di Google** (admin.google.com)

2. Passare a **Account**  >  **Domains**  >  **Manage Domains**

3. Selezionare **Aggiungi un dominio**

4. Immettere il nome di dominio selezionato

5. Seleziona **dominio alias utente**

6. Selezionare **Aggiungi dominio & avviare la verifica**

7. Attendere il completamento della verifica e aggiornare la pagina

8. Seleziona **Attiva Gmail**

9. Scegliere **Ignora configurazione record MX** e quindi selezionare **AVANTI**

10. Nella finestra **di** dialogo Instradare la posta a un altro server prendere nota del server a cui instradare la posta (ad esempio, aspmx.l.google.com) e selezionare Uso un **altro server della posta**

***Consentire ai messaggi di posta elettronica Microsoft 365 di ignorare il filtro della posta indesiderata***

1. Trovare un'intestazione appropriata dal tenant Microsoft 365 inviando un messaggio di posta elettronica a un utente nell'area di lavoro di Google.

2. Aprire il messaggio e selezionare **Mostra originale**

3. Scegliere un'intestazione di posta elettronica che identifichi in modo univoco i messaggi provenienti Microsoft 365 tenant. (Ad esempio, X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

4. Passare alla **Console di amministrazione di Google** all'indirizzo <https://admin.google.com>

5. Passare a App  >  **Google Workspace** Conformità  >  **Gmail**  >  

6. Passare a **Conformità contenuto** e selezionare **Configura**

7. Assegnare un nome all'impostazione. Ad esempio, Allowlist Microsoft 365 e-mail.

8. In Messaggi **di posta elettronica per influire sul** controllo in ingresso

9. In **Aggiungi espressioni che descrivono il contenuto** da cercare in ogni messaggio selezionare se una delle espressioni seguenti corrisponde al **messaggio**

10. In **Espressioni** selezionare **Aggiungi** xi. In **Aggiungi impostazione** scegliere Corrispondenza contenuto **avanzato**

11. In **Posizione** scegliere **Intestazioni complete**

12. In **Tipo di corrispondenza** scegliere Testo **completo**

13. In Contenuto immettere l'intestazione di posta elettronica che identifica in modo univoco i messaggi provenienti dal tenant di Microsoft 365, ad esempio X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

14. Selezionare **Salva**

15. In Se **le espressioni precedenti corrispondono,** eseguire il campo seguente > **Modifica** messaggio e selezionare Ignora filtro posta indesiderata per questo messaggio **in** **Posta indesiderata**.

16. Selezionare **Salva**

**Passaggio 4: Configurare Microsoft 365 per l'integrazione**

*Configurare il connettore per instradare la posta Microsoft 365 a Gmail:*

1. Passare **all'interfaccia di amministrazione Microsoft** all'indirizzo <https://admin.microsoft.com/AdminPortal>

2. Selezionare **Mostra tutto** nel menu di spostamento a sinistra.

3. In **Interfaccia di amministrazione** selezionare Exchange per aprire l'Exchange di amministrazione in una nuova scheda 

4. Nel menu **Exchange** di spostamento sinistro dell'interfaccia di amministrazione selezionare Connettori flusso di posta , aprire il menu di riversamento (...) e  >  selezionare Aggiungi connettore

5. In **Connessione da** nella finestra del nuovo connettore selezionare Office 365 

6. In **Connessione per selezionare** il server di posta elettronica dell'organizzazione selezionare **Avanti**

7. Immettere un **nome** per il nuovo connettore (Ad esempio: A Gmail) e continuare **Avanti**

8. Nella sezione **Uso del connettore** selezionare Solo se è impostata una regola di trasporto che reindirizza i messaggi **a questo** connettore e quindi scegliere **Avanti**.

9. Nella sezione Routing immettere lo Smart Mail Host appropriato, ad esempio aspmx.l.google.com, selezionare **+** e quindi continuare **Avanti.**

10. Nella sezione **Restrizioni di sicurezza** accettare le impostazioni predefinite selezionando **Avanti**

11. Nella sezione **Messaggio di** posta elettronica di convalida immettere un indirizzo di posta elettronica valido per il sistema Gmail, ad esempio johannal@g.contosolandscaping2.m365master.com, selezionare il segno più **(+)** e quindi selezionare **Convalida**

12. Attendere il completamento della convalida e, in caso di esito positivo, premere Avanti

13. In **Verifica connettore** verificare che la configurazione sia corretta e premere Crea connettore

14. Quando viene visualizzata la notifica Connettore creato, premere **Fine**

*Inoltrare posta da Microsoft 365 cassette postali a Gmail*

1. Usare il **Amministrazione Microsoft 365 Center** per aggiornare ogni cassetta postale oppure è possibile usare uno script **di PowerShell,** ad esempio:

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    
    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    } 
    ```

*Configurare Exchange Online di trasporto diretta al calendario*

1. La configurazione di questa impostazione consente di accettare automaticamente gli inviti al calendario in modo che siano visualizzati nel calendario Teams senza richiedere agli utenti di interagire con l'invito in Outlook Web App.

2. Lo script seguente può essere usato per creare le regole di trasporto:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems
    
    ```

*Disabilitare Outlook sul web per le cassette postali*

1. Seguire le istruzioni in [Disabilitare Outlook sul web per una](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app&preserve-view=true) cassetta postale in Exchange Online disabilitare Outlook sul web per le cassette postali.

2. È possibile disabilitare Outlook sul web **l'interfaccia di amministrazione di Exchange** o **PowerShell.** È possibile usare l'esempio di PowerShell seguente per disabilitare Outlook sul web per tutte le cassette postali:

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

**Passaggio 5: Configurare il Exchange Online per l'inoltro interno**

Questo passaggio assicura che la posta elettronica sia inviata a un sistema di terze parti per la risoluzione finale.

1. Passare **all'interfaccia di amministrazione Microsoft** all'indirizzo <https://admin.microsoft.com/AdminPortal>

2. Nel riquadro di spostamento a sinistra selezionare **Mostra tutto**

3. In **Interfaccia di amministrazione** selezionare Exchange per aprire Exchange di amministrazione in una nuova scheda 

4. **Nell Exchange di amministrazione** selezionare **Flusso** di posta dal menu di spostamento a sinistra, quindi selezionare **Domini accettati**

5. Toccare il nome di dominio configurato nel sistema di terze parti, ad esempio contosoLandscaping2.m365master.com.

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="Immagine che mostra le Exchange dell'interfaccia di amministrazione per il flusso di posta.":::

6. Selezionare **Inoltro interno,** quindi fare clic su **Salva**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Immagine che mostra l'azione di salvataggio dell'impostazione dell'inoltro interno.":::

**Passaggio 6: Creare una regola per eliminare tutti i messaggi in ingresso Exchange Online ad eccezione di Calendaring**

1. È possibile configurare questa regola **nell'Exchange di amministrazione di** **PowerShell.** È possibile usare l'esempio **di PowerShell** seguente per creare la regola:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true 
    
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>Connessione Teams Essentials alla posta elettronica di terze parti che non usa vanity domain (esempio Gmail)

È possibile pianificare e partecipare a una riunione di Teams direttamente da Google Workspace connettendo un account Gmail consumer a Teams Essentials con l'affidamento principale sul componente aggiuntivo [di Teams G Suite.](https://support.microsoft.com/en-us/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60) In questo modo è possibile pianificare videoconferenze con condivisione dello schermo, chat delle riunioni, lavagne digitali e altro ancora.

Gmail verrà configurato in modo da estrarre la posta Exchange Online posta elettronica per assicurarsi che la posta generata Microsoft 365 e Teams arrivino correttamente in Gmail. Per eseguire questa connessione, potrebbe essere necessario che le impostazioni predefinite di sicurezza siano disabilitate, quindi è essenziale usare una password univoca complessa. Un dominio personalizzato non è necessario per questo scenario, ma può essere configurato in Microsoft 365 per l'uso in Gmail se si vuole usarlo.

:::image type="content" source="media/essentials-gmail.png" alt-text="Immagine che impovere il flusso di posta tra Teams Essentials e Gmail":::

**Assicurarsi di avere configurato un account Gmail.**

Se si ha già un account esistente, è possibile procedere con il passaggio successivo. In caso contrario, visita [Crea nuovo account Google](https://accounts.google.com/SignUp?hl=en) per configurare un nuovo account Gmail.

**2. Configurare il tenant Microsoft 365 tenant**

*Configurare Teams AAD utenti*

1. Seguire le istruzioni in[Aggiungere utenti e assegnare licenze](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) per aggiungere più utenti

*Configurare la protezione delle identità*

1. Disabilitare le impostazioni predefinite di sicurezza, se attive.

2. Configurare l'autenticazione a più fattori per gli utenti

3. Se si usa l'accesso condizionale, assicurarsi di fare un'eccezione per l'accesso POP alla cassetta postale

*Aggiungere un dominio al Amministrazione Microsoft 365 Center (facoltativo)*

1. Nella barra di spostamento selezionare Impostazioni > dominio, quindi selezionare Aggiungi dominio

2. Immettere il nome di dominio nel campo appropriato

3. Seguire le istruzioni visualizzate per verificare il dominio con il record TXT

4. Quando richiesto, consentire a Microsoft di configurare il DNS

5. Completare le istruzioni per verificare la route del record MX Microsoft 365

6. Configurare il record TXT SPF in modo da includere Microsoft 365

7. Completare le istruzioni per la configurazione dei record TXT DKIM per Microsoft 365

8. Verificare che DKIM sia abilitato disconnettendoti e accedendo di nuovo all'interfaccia di amministrazione

**3. Configurare Gmail**

1. Configurare Gmail in modo da Exchange Online posta elettronica nel sistema

2. Configurare il Teams calendario

3. Abilitare Gmail per l'uso del dominio aziendale (facoltativo)
