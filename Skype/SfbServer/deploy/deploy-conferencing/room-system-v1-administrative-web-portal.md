---
title: Distribuire il portale Web amministrativo di SRS V1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Il portale Web di amministrazione di Skype for Business Server Skype (SRS V1, precedentemente noto come Lync room System) è un portale Web che può essere utilizzato dalle organizzazioni per gestire le sale conferenze dei sistemi in sala Skype. Gli amministratori possono utilizzare il portale Web amministrativo di SRS V1 per monitorare l'integrità del dispositivo, ad esempio monitorando i dispositivi audio/video. Con questo portale, gli amministratori possono raccogliere informazioni diagnostiche in remoto per monitorare l'integrità della sala riunioni.
ms.openlocfilehash: d718adb60437fdd7e08724a5ba5fc48fa120425e
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "42045899"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Distribuire il portale Web amministrativo di SRS V1 in Skype for Business Server

Il portale Web di amministrazione di Skype for Business Server Skype (SRS V1, precedentemente noto come Lync room System) è un portale Web che può essere utilizzato dalle organizzazioni per gestire le sale conferenze dei sistemi in sala Skype. Gli amministratori possono utilizzare il portale Web amministrativo di SRS V1 per monitorare l'integrità del dispositivo, ad esempio monitorando i dispositivi audio/video. Con questo portale, gli amministratori possono raccogliere informazioni diagnostiche in remoto per monitorare l'integrità della sala riunioni.

Per utilizzare questa funzionalità, è necessario distribuire il portale Web amministrativo SRS V1 su tutti i server front end di Skype for Business Server. In questa guida vengono fornite istruzioni per gli amministratori su come installare e configurare il portale Web amministrativo SRS. È destinato agli amministratori che dispongono della conoscenza dell'amministrazione di Skype for Business Server e che dispongono di diritti utente di amministratore per modificare la topologia di Skype for Business Server.

Dopo che il portale Web amministrativo SRS V1 è stato distribuito sul server, gli amministratori possono controllare i dispositivi SRS V1 di stato accedendo al sito dai propri computer o laptop.

> [!IMPORTANT]
> Scaricare il [portale Web amministrativo per Skype for Business Server 2015 di Microsoft Skype room Systems V1](https://www.microsoft.com/download/details.aspx?id=46906).

Contenuto dell'argomento:

- [Configurare l'ambiente per il portale Web amministrativo di SRS V1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Installare il portale Web amministrativo di SRS V1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Utilizzare il portale Web amministrativo SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Configurare l'ambiente per il portale Web amministrativo di SRS V1
<a name="Config_Env"> </a>

Per utilizzare il portale Web amministrativo SRS V1, è necessario installare o configurare i prerequisiti seguenti.

> [!IMPORTANT]
> Se il server è configurato con l'autenticazione Kerberos e NTLM e l'interfaccia SRS è in esecuzione in un computer che non è stato aggiunto al dominio, l'autenticazione Kerberos avrà esito negativo e l'utente non visualizzerà lo stato del servizio SRS nel portale amministrativo. Per risolvere il problema, configurare il server con l'autenticazione NTLM o sia l'autenticazione NTLM che TLS-DSK (senza Kerberos) oppure aggiungere il computer SRS al dominio.

1. Installare gli aggiornamenti cumulativi di Skype for Business Server nella topologia di Skype for Business Server.

    Per ottenere l'aggiornamento o vedere cosa è incluso in esso, vedere [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

2. Creare un utente di Active Directory abilitato per SIP.

    Il portale Web amministrativo SRS V1 utilizza queste credenziali per eseguire query su informazioni da Skype for Business Server. Il nome utente negli esempi specificati è LRSApp.

3. Creare un gruppo di sicurezza di Active Directory con nome LRSSupportAdminGroup.

    Creare il gruppo con ambito gruppo come globale e come tipo di gruppo come protezione. Gli utenti abilitati per SIP che sono stati aggiunti a questo gruppo saranno autorizzati a visualizzare l'elenco delle sale ed eseguire alcuni comandi, ad esempio la raccolta di registri.

4. Creare un gruppo di sicurezza di Active Directory con nome LRSFullAccessAdminGroup.

    Creare il gruppo con ambito gruppo come globale e come tipo di gruppo come protezione. gli utenti abilitati per SIP aggiunti a questo gruppo sono autorizzati a utilizzare tutte le funzionalità del portale di amministrazione in una singola sala Skype. Per includere il supporto per la gestione in blocco delle sale Skype, fare riferimento al passaggio 5.

     ![Elenco dei gruppi di amministratori con il ruolo di gruppo di sicurezza](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Creare un gruppo di sicurezza di Active Directory con nome LRSPowerUserAdminsGroup.

    Creare il gruppo con ambito gruppo come globale e come tipo di gruppo come protezione. Gli utenti abilitati al SIP che sono stati aggiunti a questo gruppo sono autorizzati a utilizzare tutte le funzionalità del portale di amministrazione, inclusa la gestione in blocco delle sale di Skype for business.

6. Aggiungere LRSFullAccessAdminGroup come membro di LRSSupportAdminGroup.

     ![Pagina membri proprietà LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Creare un utente di Active Directory SIP abilitato con nome LRSSupport. Aggiungere l'utente a LRSSupportAdminGroup.

     ![Pagina membri proprietà LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Installare [ASP.NET MVC 4 per Visual Studio 2010 SP1 e Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).

## <a name="install-the-srs-v1-administrative-web-portal"></a>Installare il portale Web amministrativo di SRS V1
<a name="Install_SRS"> </a>

Scaricare il [portale Web amministrativo per Skype for Business Server 2015 di Microsoft Skype room Systems V1](https://www.microsoft.com/download/details.aspx?id=46906).

Per installare il portale Web amministrativo di SRS V1, attenersi alla seguente procedura.

1. Configurare la porta dell'applicazione attendibile eseguendo il cmdlet seguente in Skype for Business Server Management Shell:

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Per installare il portale della sala riunioni, scaricare **MeetingRoomPortalInstaller. msi** e quindi eseguirlo come amministratore.

3. Aprire il file Web. config dal percorso seguente:

    % Program Files%\Skype for Business Server 2015 \ Web Components\Meeting room Portal\Int\Handler\

4. Nel file Web. config modificare PortalUserName con il nome utente creato nel passaggio 2 sotto la sezione "[Configure your environment for the SRS V1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (il nome consigliato nel passaggio è LRSApp):

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Poiché il portale di amministrazione di SRS V1 è un'applicazione attendibile, non è necessario fornire la password nella configurazione del portale. Se l'utente utilizza un registrar diverso da quello locale, è necessario specificare il registrar per il servizio di registrazione aggiungendo la riga seguente nel file Web. config:

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Se la porta utilizzata è diversa da 5061, aggiungere la riga seguente nel file Web. config:

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Verificare l'installazione del portale Web amministrativo di SRS

Per verificare l'installazione del portale Web amministrativo di SRS V1, eseguire le operazioni seguenti:

1. In un front end Server passare all'URL seguente:

    https:// \<fe-server\> /LRS

    Non è possibile visualizzare errori, come illustrato nell'immagine seguente:

     ![Schermata di accesso al portale di amministrazione di Lync room System](../../media/LRS_AdminPortalSignIn.png)

2. Se non vengono visualizzati errori, provare a accedere all'URL seguente da qualsiasi altro computer della topologia:

    https:// \<fe-server\> /LRS

    Per accedere alla pagina, sarà necessario aggiungere i record DNS come descritto in "[record DNS necessari per](https://go.microsoft.com/fwlink/p/?LinkId=318056)l'accesso automatico dei client".

## <a name="use-the-srs-administrative-web-portal"></a>Utilizzare il portale Web amministrativo SRS
<a name="Use_Portal"> </a>

Dopo aver distribuito il servizio SRS nel server, è possibile controllare lo stato di tutte le stanze SRS accedendo al portale Web amministrativo SRS V1 da un browser.

### <a name="sign-in"></a>Accesso

1. Passare all'URL seguente:

    https:// \<fe-server\> /LRS

2. Immettere le credenziali per l'account di LRSSupport o un account aggiunto al gruppo di sicurezza di LRSSupportAdminGroup.

![Schermata di accesso al portale di amministrazione di Lync room System](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Pagina di riepilogo del portale Web amministrativo SRS

Nella pagina Riepilogo sono disponibili le informazioni seguenti per tutte le stanze SRS distribuite nel server:

- **Tag** Nome personalizzato che viene fornito dall'amministratore per la sala. Il tag può essere impostato nel portale facendo clic sul nome della sala.

- **Integrità** Lo stato di integrità della sala, che deriva dallo stato di integrità di aggregazione della sala, visualizzata nella sezione integrità della pagina impostazioni sala.

- **Prossima riunione** Data e ora in cui viene pianificata la riunione successiva.

- **Versione SRS, produttore, modello** Questi valori sono preimpostati in SRS. A seconda del produttore, questi campi potrebbero essere lasciati vuoti.

- **Ultimo aggiornamento** Visualizza l'ultima volta che la pagina Web è stata aggiornata.

![Visualizzazione di riepilogo del portale di amministrazione di Lync room System](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Se si fa parte del gruppo di sicurezza di LRSPowerUserAdminsGroup, verrà visualizzato solo il menu gestione in blocco.

### <a name="srs-room-information"></a>Informazioni sulla sala SRS

La sezione informazioni sala del portale consente di visualizzare e configurare le singole stanze SRS. Contiene quattro sezioni: impostazioni, dettagli, registrazione e integrità.

#### <a name="settings"></a>Impostazioni

Nella sezione impostazioni è possibile impostare la password, il tag sala e i livelli di volume predefiniti per la sala. Se si configurano queste impostazioni, le modifiche vengono replicate solo dopo aver riavviato la console SRS. Verranno visualizzate solo le impostazioni degli aggiornamenti di sistema per i dispositivi SRS che utilizzano la versione 15,12 e versioni successive.

![Impostazioni delle sale del portale di amministrazione di Lync room System](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Dettagli

La sezione dettagli fornisce un riepilogo di sola lettura delle impostazioni della sala SRS, tra cui: l'ora dell'ultimo aggiornamento. prossima riunione; ultimi aggiornamenti, manutenzione e calibrazione; impostazioni predefinite per altoparlanti, MIC e suonerie; versione URI SIP; numero di schermate e dettagli relativi a ogni schermata; stato e attività.

![Visualizzazione dettagli del portale di amministrazione di Lync room System](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Risoluzione dei problemi

La sezione risoluzione dei problemi può essere utilizzata per raccogliere i log in remoto e salvarli in una posizione specificata. È inoltre possibile riavviare la console SRS (interfaccia utente SRS) o riavviare l'intero sistema. Per raccogliere i registri, specificare un percorso di cartella nel formato specificato e verificare che la cartella disponga delle autorizzazioni di scrittura concesse all'account del computer SRS. Se la dimensione del registro è troppo grande, è possibile richiedere fino a 5 minuti per completare la raccolta dei registri. L'aggiornamento della pagina consente di ottenere lo stato più recente.

#### <a name="health"></a>Sanità

La sezione Health fornisce un'indicazione visiva dell'integrità della connessione di Skype for Business Server, del dispositivo audio, del dispositivo video, dello stato di resilienza e del dispositivo schermo.

![Integrità della sala del portale di amministrazione di Lync room System](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Note aggiuntive sul portale Web amministrativo

> [!NOTE]
>  Le modifiche apportate alle impostazioni vengono applicate solo dopo il riavvio del sistema SRS. > se la password dell'account LRSApp scade, non sarà possibile visualizzare lo stato delle chat room. Configurare la password dell'account LRSAppuser in modo che non scada mai o accertarsi di aggiornare la password al termine della scadenza. > il portale Web amministrativo SRS è supportato solo per le distribuzioni locali.

### <a name="bulk-management"></a>Gestione in blocco

La gestione in blocco delle sale SRS è una funzionalità progettata per gli amministratori IT avanzati, per semplificare il flusso di lavoro e per consentire loro di gestire in remoto più ambienti in modo più semplice.

Per visualizzare questa funzionalità, è necessario eseguire il provisioning dell'utente come membro del gruppo di sicurezza speciale **LRSPowerUserAdminsGroup**.

Non esiste alcun limite al numero di stanze SRS che è possibile selezionare per la gestione in blocco. Tuttavia, è possibile eseguire una sola operazione di gestione in blocco alla volta.

Per eseguire un'operazione di gestione in blocco, selezionare le sale che si desidera monitorare e fare clic sul menu gestione in blocco.

### <a name="frequently-asked-questions"></a>Domande frequenti

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Perché non è possibile accedere al portale Web amministrativo?

Quando si apre https://localhost/lrs , si sarà in grado di visualizzare la pagina di accesso, ma quando si digita le credenziali, non è possibile accedere. In questo caso, è necessario aprire https://FQDNofFEserver/SRS per accedere al portale Web amministrativo.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>Perché non è possibile visualizzare il servizio SRS V1 nel portale Web di amministrazione?

- Verificare di disporre degli account SRS nella distribuzione e che vengano creati in base ai suggerimenti relativi alla distribuzione del portale Web amministrativo di SRS. Verificare che gli account SRS siano stati provisionati usando Enable-CsMeetingRoom, not Enable-CsUser, su Skype for Business Server.

- Se sono stati creati account SRS e non è possibile visualizzare gli account nel portale Web amministrativo, raccogliere i registri del server utilizzando lo strumento di registrazione di Skype for Business Server con il componente **MeetingPortal** selezionato e quindi inviarli al contatto di supporto SRS.

- Se sono stati creati account SRS e non è possibile visualizzare gli account nel portale Web amministrativo, raccogliere i registri client utilizzando Fiddler e copiare anche il registro della console dagli strumenti di sviluppo del browser e quindi inviarli al contatto di supporto SRS. È inoltre possibile modificare il valore del livello di traccia nel file Web. config per ottenere un log più dettagliato.

  ```xml
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>Perché non è possibile visualizzare lo stato di SRS nel portale Web di amministrazione?

- Verificare che l'account utente di LRSApp sia abilitato per SIP.

- Se si verificano ancora problemi, raccogliere il file **Trace. log** nel sistema SRS da D:\Tracing\LRSAdminLogs \, e quindi inviarlo al contatto di supporto SRS.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>Perché non è possibile visualizzare i menu di gestione di massa per il servizio SRS nel portale Web di amministrazione?

Assicurarsi che l'account utente di LRSApp sia abilitato per SIP e faccia parte del gruppo di sicurezza LRSPowerUserAdminsGroup.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>Il portale Web amministrativo SRS V1 funziona con le sale di Microsoft Teams?

No.


