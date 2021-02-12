---
title: Distribuire il portale Web amministrativo di SRS v1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Il portale Web amministrativo di Skype for Business Server Skype Room Systems v1 (SRS v1, in precedenza noto come Lync Room System) è un portale Web che le organizzazioni possono usare per gestire le proprie sale riunioni Skype Room Systems. Gli amministratori possono utilizzare il portale Web amministrativo di SRS v1 per monitorare l'integrità dei dispositivi, ad esempio monitorando i dispositivi audio/video. Con questo portale, gli amministratori possono raccogliere in remoto informazioni di diagnostica per monitorare l'integrità delle sale riunioni.
ms.openlocfilehash: 7d7bef99149d09ebf72c9b633370f262e535b23f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804536"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Distribuire il portale Web amministrativo di SRS v1 in Skype for Business Server

Il portale Web amministrativo di Skype for Business Server Skype Room Systems v1 (SRS v1, in precedenza noto come Lync Room System) è un portale Web che le organizzazioni possono usare per gestire le proprie sale riunioni Skype Room Systems. Gli amministratori possono utilizzare il portale Web amministrativo di SRS v1 per monitorare l'integrità dei dispositivi, ad esempio monitorando i dispositivi audio/video. Con questo portale, gli amministratori possono raccogliere in remoto informazioni di diagnostica per monitorare l'integrità delle sale riunioni.

Per usare questa funzionalità, il portale Web amministrativo di SRS v1 deve essere distribuito in ogni Front End Server di Skype for Business Server. In questa guida vengono fornite istruzioni per gli amministratori su come installare e configurare il portale Web amministrativo di SRS. È destinato agli amministratori che hanno una conoscenza dell'amministrazione di Skype for Business Server e che dispongono dei diritti di amministratore per modificare la topologia di Skype for Business Server.

Dopo la distribuzione del portale Web amministrativo SRS v1 nel server, gli amministratori possono controllare lo stato dei dispositivi SRS v1 accedendo al sito dai propri computer o laptop.

> [!IMPORTANT]
> Scaricare il portale Web di amministrazione di [Microsoft Skype Room Systems v1 per Skype for Business Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)

Contenuto dell'argomento:

- [Configurare l'ambiente per il portale Web amministrativo di SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Installare il portale Web amministrativo di SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Usare il portale Web amministrativo di SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Configurare l'ambiente per il portale Web amministrativo di SRS v1
<a name="Config_Env"> </a>

Per utilizzare il portale Web amministrativo di SRS v1, è necessario installare o configurare i prerequisiti seguenti.

> [!IMPORTANT]
> Se il server è configurato con l'autenticazione Kerberos e NTLM e SRS è in esecuzione in un computer non appartenente al dominio, l'autenticazione Kerberos avrà esito negativo e l'utente non sarà in grado di visualizzare lo stato di SRS nel portale amministrativo. Per risolvere questo problema, configurare il server con l'autenticazione NTLM o l'autenticazione NTLM e TLS-DSK (senza Kerberos) oppure aggiungere il computer SRS al dominio.

1. Installare gli aggiornamenti cumulativi di Skype for Business Server nella topologia di Skype for Business Server.

    Per ottenere l'aggiornamento o vedere cosa include, vedere [Aggiornamenti per Skype for Business Server 2015.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)

2. Creare un utente di Active Directory abilitato per SIP.

    Il portale Web amministrativo di SRS v1 usa queste credenziali per eseguire query sulle informazioni da Skype for Business Server. Il nome utente negli esempi forniti è LRSApp.

3. Creare un gruppo di sicurezza di Active Directory con nome LRSSupportAdminGroup.

    Creare il gruppo con Ambito gruppo come Globale e Tipo di gruppo come sicurezza. Gli utenti abilitati per SIP aggiunti a questo gruppo saranno autorizzati a visualizzare l'elenco delle chat room ed eseguire determinati comandi, ad esempio la raccolta dei registri.

4. Creare un gruppo di sicurezza di Active Directory con nome LRSFullAccessAdminGroup.

    Creare il gruppo con Ambito di gruppo come Globale e Tipo di gruppo come Security.SIP gli utenti che vengono aggiunti a questo gruppo sono autorizzati a usare tutte le funzionalità del portale di amministrazione in una singola chat room Skype. Per includere il supporto per la gestione in blocco delle sale Skype, fare riferimento al passaggio 5.

     ![Elenco dei gruppi di amministratori con ruolo gruppo di sicurezza](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Creare un gruppo di sicurezza di Active Directory con nome LRSPowerUserAdminsGroup.

    Creare il gruppo con Ambito gruppo come Globale e Tipo di gruppo come sicurezza. Gli utenti abilitati per SIP aggiunti a questo gruppo sono autorizzati a utilizzare tutte le funzionalità del portale di amministrazione, inclusa la gestione in blocco delle sale skype for business.

6. Aggiungere LRSFullAccessAdminGroup come membro di LRSSupportAdminGroup.

     ![Pagina membri delle proprietà LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Creare un utente di Active Directory abilitato per SIP con nome LRSSupport. Aggiungi questo utente a LRSSupportAdminGroup.

     ![Pagina membri delle proprietà LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Installare [ASP.NET MVC 4 per Visual Studio 2010 SP1 e Visual Web Developer 2010 SP1.](https://go.microsoft.com/fwlink/p/?LinkId=323967)

## <a name="install-the-srs-v1-administrative-web-portal"></a>Installare il portale Web amministrativo di SRS v1
<a name="Install_SRS"> </a>

Scaricare il portale Web di amministrazione di [Microsoft Skype Room Systems v1 per Skype for Business Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)

Per installare il portale Web amministrativo di SRS v1, eseguire la procedura seguente.

1. Configurare la porta dell'applicazione attendibile eseguendo il cmdlet seguente in Skype for Business Server Management Shell:

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Per installare il portale della sala riunioni, scaricare **MeetingRoomPortalInstaller.msi** ed eseguirlo come amministratore.

3. Aprire il Web.config file dal percorso seguente:

    %Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\

4. Nel file Web.Config modificare PortalUserName con il nome utente creato nel passaggio 2 nella sezione " Configurare l'ambiente per il portale Web amministrativo[di SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (il nome consigliato nel passaggio è LRSApp):

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Poiché il portale di amministrazione di SRS v1 è un'applicazione attendibile, non è necessario fornire la password nella configurazione del portale. Se l'utente utilizza un registrar diverso da quello locale, è necessario specificarlo aggiungendo la riga seguente nel file Web.Config:

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Se la porta utilizzata è diversa da 5061, aggiungere la riga seguente nel file Web.Config seguente:

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Verificare l'installazione del portale Web amministrativo di SRS

Per verificare l'installazione del portale Web amministrativo di SRS v1, eseguire le operazioni seguenti:

1. In un Front End Server passare all'URL seguente:

    https:// \<fe-server\> /lrs

    Non dovrebbero essere visualizzati errori, come illustrato nell'immagine seguente:

     ![Schermata di accesso al portale di amministrazione di Lync Room System](../../media/LRS_AdminPortalSignIn.png)

2. Se non vengono visualizzati errori, provare ad accedere all'URL seguente da qualsiasi altro computer della topologia:

    https:// \<fe-server\> /lrs

    Per accedere alla pagina, è necessario aggiungere i record DNS come descritto in "[Record DNS necessari per l'accesso](https://go.microsoft.com/fwlink/p/?LinkId=318056)automatico dei client".

## <a name="use-the-srs-administrative-web-portal"></a>Usare il portale Web amministrativo di SRS
<a name="Use_Portal"> </a>

Dopo aver distribuito SRS nel server, è possibile controllare lo stato di tutte le sale SRS accedendo al portale Web amministrativo di SRS v1 da un browser.

### <a name="sign-in"></a>Accesso

1. Passare all'URL seguente:

    https:// \<fe-server\> /lrs

2. Immettere le credenziali per l'account LRSSupport o un account aggiunto al gruppo di sicurezza LRSSupportAdminGroup.

![Schermata di accesso al portale di amministrazione di Lync Room System](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Pagina di riepilogo del portale Web amministrativo SRS

Nella pagina di riepilogo sono disponibili le informazioni seguenti per tutte le chat room SRS distribuite nel server:

- **Tag** Nome personalizzato che l'amministratore assegna alla chat room. Il tag può essere impostato nel portale facendo clic sul nome della sala.

- **Integrità** Lo stato di integrità della sala, derivato dallo stato Aggrega integrità della sala, visualizzato nella sezione Integrità della pagina Impostazioni sala.

- **Riunione successiva** Data e ora di pianificazione della riunione successiva.

- **Versione SRS, produttore, modello** Questi valori sono preimpostati in SRS. A seconda del produttore, questi campi potrebbero essere lasciati vuoti.

- **Ultimo aggiornamento** Visualizza l'ora dell'ultimo aggiornamento della pagina Web.

![Visualizzazione riepilogativo del portale di amministrazione di Lync Room System](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Il menu Gestione in blocco verrà visualizzato solo se si fa parte del gruppo di sicurezza LRSPowerUserAdminsGroup.

### <a name="srs-room-information"></a>Informazioni sala SRS

La sezione Informazioni sala del portale consente di visualizzare e configurare singole sale SRS. Contiene quattro sezioni: Impostazioni, Dettagli, Registrazione e Integrità.

#### <a name="settings"></a>Impostazioni

Nella sezione Impostazioni puoi impostare la password, il tag sala e i livelli di volume predefiniti per la sala. Se si configurano queste impostazioni, le modifiche vengono replicate solo dopo il riavvio della console di SRS. Verranno visualizzati solo gli aggiornamenti di sistema per i dispositivi SRS con la versione 15.12 e successive.

![Impostazioni della sala del portale di amministrazione di Lync Room System](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Dettagli

La sezione Dettagli fornisce un riepilogo di sola lettura delle impostazioni della sala SRS, tra cui: l'ora dell'ultimo aggiornamento; riunione successiva; ultimi aggiornamenti, manutenzione e calibrazione; impostazioni predefinite per altoparlante, microfono e suoneria; version; URI SIP; numero di schermate e dettagli su ogni schermata; stato e attività.

![Visualizzazione dettagli portale di amministrazione di Lync Room System](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Risoluzione dei problemi

La sezione Risoluzione dei problemi può essere utilizzata per raccogliere in remoto i log e salvarli in un percorso specificato. Puoi anche riavviare la console SRS (interfaccia utente SRS) o l'intero sistema. Per raccogliere i registri, specificare un percorso di cartella nel formato specificato e assicurarsi che la cartella abbia le autorizzazioni di scrittura concesse all'account del computer SRS. Se le dimensioni del registro sono troppo grandi, la raccolta dei registri può richiedere fino a 5 minuti. L'aggiornamento della pagina consente di visualizzare lo stato più recente.

#### <a name="health"></a>Sanità

La sezione Integrità fornisce un'indicazione visiva dell'integrità della connessione a Skype for Business Server, del dispositivo audio, del dispositivo video, dello stato di resilienza e del dispositivo schermo.

![Lync Room System Admin Portal Room Health](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Note aggiuntive sul portale Web amministrativo

> [!NOTE]
>  Le modifiche alle impostazioni vengono applicate solo dopo il riavvio del sistema SRS.> Se la password dell'account LRSApp scade, non sarà possibile visualizzare lo stato delle chat room. Configurare la password dell'account LRSAppuser in modo che non scada mai o assicurarsi di aggiornarla quando è quasi scaduta.> Il portale Web amministrativo di SRS è supportato solo per le distribuzioni locali.

### <a name="bulk-management"></a>Gestione in blocco

La gestione in blocco delle sale SRS è una funzionalità progettata per gli amministratori IT avanzati, per semplificare il flusso di lavoro e consentire loro di utilizzare un pratico strumento che consente di risparmiare tempo per gestire in remoto più sale in blocco.

Per visualizzare questa funzionalità, è necessario eseguire il provisioning dell'utente come membro del gruppo di sicurezza **speciale, LRSPowerUserAdminsGroup.**

Non esiste alcun limite al numero di sale SRS che è possibile selezionare per la gestione in blocco. Tuttavia, è possibile eseguire una sola operazione di gestione in blocco alla volta.

Per eseguire un'operazione di gestione in blocco, selezionare le chat room che si desidera monitorare e fare clic sul menu Gestione in blocco.

### <a name="frequently-asked-questions"></a>Domande frequenti

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Perché non è possibile accedere al portale Web amministrativo?

Quando si apre , sarà possibile visualizzare la pagina di accesso, ma quando si digitano le credenziali, non è https://localhost/lrs possibile accedere. In questo caso, è necessario aprire https://FQDNofFEserver/SRS per accedere al portale Web amministrativo.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>Perché non è possibile visualizzare SRS v1 nel portale Web amministrativo?

- Assicurarsi di disporre di account SRS nella distribuzione e che siano creati in base alle indicazioni per la distribuzione del portale Web amministrativo di SRS. Assicurarsi che il provisioning degli account SRS sia eseguito utilizzando Enable-CsMeetingRoom, non Enable-CsUser, in Skype for Business Server.

- Se sono stati creati account SRS e non è possibile visualizzare gli account nel portale Web amministrativo, raccogliere i log del server utilizzando lo strumento di registrazione di Skype for Business Server con il **componente MeetingPortal** selezionato, quindi inviarli al contatto di supporto SRS.

- Se hai creato account SRS e non puoi vedere gli account nel portale Web amministrativo, raccogli i log client con Fiddler e copia anche il log della console dagli strumenti di sviluppo del browser e quindi inviali al contatto di supporto SRS. È inoltre possibile modificare il valore del livello di traccia nella Web.config per ottenere un registro più dettagliato.

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>Perché non è possibile visualizzare lo stato di SRS nel portale Web amministrativo?

- Verificare che l'account utente LRSApp sia abilitato per SIP.

- If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs \, and then send it to your SRS support contact.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>Perché non è possibile visualizzare i menu di gestione in blocco per SRS nel portale Web amministrativo?

Verificare che l'account utente LRSApp sia abilitato per SIP e che sia parte del gruppo di sicurezza LRSPowerUserAdminsGroup.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>Il portale Web amministrativo di SRS v1 funziona con Microsoft Teams Rooms?

No.


