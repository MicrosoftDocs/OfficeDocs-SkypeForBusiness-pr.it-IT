---
title: Risoluzione dei problemi di accesso a Skype for Business online (amministratori)
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Setup
description: 'Scopri le cause più comuni per Skype di errori di accesso Business online e il lavoro e risolvere questi problemi. '
ms.openlocfilehash: 25f6c08392823c35e4bb5d53ac523c1efeddf958
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285035"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>Risoluzione dei problemi di accesso a Skype for Business online (amministratori)

Per risolvere i problemi di accesso a Skype for Business online problemi, è bene iniziare eliminando le cause più comuni dei problemi di accesso. Se necessario, è possibile seguire una procedura di risoluzione specifica in base al tipo di errore. Se non è ancora possibile accedere, raccogliere nuove informazioni e chiedere ulteriore assistenza.

## <a name="what-do-you-want-to-do"></a>Quale operazione si desidera effettuare?
<a name="top"> </a>

> [Cercare le cause più comuni dei problemi di accesso di Skype for Business online ](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
> 
> [Eseguire le procedure di risoluzione per un errore specifico (solo Enterprise)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
> 
> [Aggiungere una voce del firewall per msoidsvc.exe al server proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
> 
> [Aggiornare le impostazioni DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
> 
> [Installare un certificato SSL di terze parti nel server ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
> 
> [Aggiornare le credenziali di sicurezza](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
> 
> [Modificare le chiavi TrustModelData del Registro di sistema](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
> 
> [Aggiornare le impostazioni utente in Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
> 
> [Usare la guida alla risoluzione dei problemi del supporto tecnico Microsoft](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
> 
> [Raccogliere ulteriori informazioni e richiedere assistenza](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Cercare le cause più comuni dei problemi di accesso di Skype for Business online
<a name="toc323194094"> </a>

La maggior parte dei problemi di accesso rientrano in un numero limitato di cause, molte delle quali risolvibili in modo semplice. La tabella seguente elenca le cause comuni dei problemi di accesso e alcune operazioni che gli utenti possono effettuare per risolverli.


| **Causa possibile**                                                                                                                                                    | **Risoluzione**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Durante l’accesso viene visualizzata una finestra di dialogo che contiene la frase seguente: ** Impossibile verificare l'attendibilità del server per l'indirizzo di accesso. Connettersi comunque?** <br/> | Verificare che il nome di dominio nella finestra di dialogo sia un server attendibile dell'organizzazione, ad esempio, **nomedominio.contoso.com**. Chiedere all'utente di selezionare la **Considera il server sempre attendibile**, quindi fare clic su **Connetti**. <br/> I clienti aziendali possono disattivare la visualizzazione di questo messaggio quando l'utente accede per la prima volta modificando il Registro di sistema di Windows nel computer di ogni utente. Per informazioni dettagliate, vedere [Modificare le chiavi TrustModelData del Registro di sistema](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).<br/> |
| Indirizzo, nome utente o password di accesso digitati in modo non corretto  <br/>                                                                                                               | Confermare che nome utente e password di accesso dell'utente siano corretti. <br/>  Verificare che il nome d’accesso dell’utente sia stato formattato nel modo seguente: <strong>bobk@contoso.com</strong>. Questo può essere diverso dal formato utilizzato per effettuare l’accesso alla rete della propria organizzazione.  <br/>  Chiedere all'utente di provare a effettuare nuovamente l’accesso. <br/>                                                                                                                                                                                                                             |
| Password dimenticata  <br/>                                                                                                                                             | Reimpostare la password dell'utente e comunicare la nuova password temporanea.  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Non si possiede la licenza per usare Skype for Business online.  <br/>                                                                                                                  | Verificare che l'utente sia registrato come utente Skype for Business online. In caso contrario, registrare l'utente e chiedere di effettuare nuovamente l’accesso.  <br/>                                                                                                                                                                                                                                                                                                                                                                                           |
| È stata installata la versione errata di Skype for Business online.  <br/>                                                                                                           | Questo problema è generalmente associato a un messaggio di errore che contiene la frase seguente: **il servizio di autenticazione non è compatibile con questa versione del programma**.  <br/> Chiedere all'utente di disinstallare e reinstallare Skype for Business online dal portale di Office 365.   <br/>                                                                                                                                                                                                                                                    |
| Problema durante l'acquisizione di un certificato personale richiesto per eseguire l'accesso  <br/>                                                                                           | Se l'indirizzo di accesso dell'utente è stato modificato di recente, è necessario eliminare i dati di accesso memorizzati nella cache. Chiedere agli utenti di disconnettersi, fare clic su Elimina il collegamento alle informazioni di accesso nella schermata di accesso e riprovare.  <br/>                                                                                                                                                                                                                                                                                                                                |
| È stato configurato un nome di dominio personalizzato ed è possibile che le modifiche non siano ancora state propagate in tutto il sistema.  <br/>                                                         | Verificare innanzitutto di aver modificato i record DNS (Domain Name Service) in modo da riflettere la modifica.  <br/> Se le modifiche DNS necessarie sono già state effettuate, chiedere all'utente di riprovare ad accedere in un secondo momento. Le modifiche DNS possono richiedere fino a 72 ore perché si riflettano in tutto il sistema.  <br/>                                                                                                                                                                                                                                                        |
| L'orologio di sistema non è sincronizzato con l'orologio del server  <br/>                                                                                                                     | Verificare che il controller di dominio di rete si sincronizzi con un'origine ora esterna affidabile. Per informazioni dettagliate, vedere l'articolo 816042 della Microsoft Knowledge Base [Configurazione di un server di riferimento ora autorevole in Windows Server](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).<br/>                                                                                                                                                                                                                                          |

Per risolvere i problemi di accesso a Skype for Business online problemi, è bene iniziare eliminando le cause più comuni dei problemi di accesso. Se necessario, è possibile seguire una procedura di risoluzione specifica in base al tipo di errore. Se non è ancora possibile accedere, raccogliere nuove informazioni e chiedere ulteriore assistenza.

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>Eseguire le procedure di risoluzione per un errore specifico (solo Enterprise)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  Queste istruzioni sono destinate principalmente ai clienti del Piano E di Microsoft Office 365. Se si è un cliente del Piano E di Microsoft Office 365, passare alla sezione seguente [Raccogliere ulteriori informazioni e richiedere assistenza](troubleshooting-sign-in-errors-for-admins.md#collect-more-information). 

Se non si riesce ad accedere dopo aver provato i suggerimenti nella sezione precedente, è possibile eseguire ulteriori operazioni per la risoluzione dei problemi in base al tipo di errore. La tabella seguente elenca i più comuni messaggi di errore e le possibili cause. La tabella di seguito contiene procedure dettagliate per ogni problema.

|**Messaggio di errore**|**Causa possibile**|**Risoluzione**|
|:-----|:-----|:-----|
|Indirizzo di accesso non trovato  <br/> |Le richieste di accesso dall'Assistente per l'accesso a Microsoft Online Services (msoidsvc.exe) non attraversano il firewall esterno o il server proxy.  <br/> |[Aggiungere una voce del firewall per msoidsvc.exe al server proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|Server temporaneamente non disponibile  <br/> |Se l'organizzazione dispone di un dominio personalizzato, è possibile che le impostazioni DNS (Domain Name System) necessarie non siano disponibili o siano errate.  <br/> |[Aggiornare le impostazioni DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|Server temporaneamente non disponibile  <br/> |Se l'organizzazione usa l'accesso Single Sign-On con Active Directory Federation Services, è possibile che sia stato usato un certificato SSL (Secure Sockets Layer) autofirmato anziché un certificato emesso da un'Autorità di certificazione di terze parti.  <br/> |[Installare un certificato SSL di terze parti nel server ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|Problema durante l'acquisizione di un certificato personale richiesto per eseguire l'accesso  <br/> |Se i dati del server memorizzati nella cache e usati da Lync per accedere sono già stati rimossi ma l'errore viene ancora visualizzato, le credenziali di sicurezza dell'utente potrebbero essere danneggiate oppure una cartella RSA nel computer dell'utente potrebbe impedire l'autenticazione.  <br/> |[Aggiornare le credenziali di sicurezza](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|Viene visualizzata una finestra di dialogo relativa all'attendibilità del certificato quando un utente accede per la prima volta.  <br/> |Questa finestra di dialogo viene visualizzata se il server Skype for Business non è ancora elencato nella chiave del Registro di sistema **TrustModelData**. <br/> |[Modificare le chiavi TrustModelData del Registro di sistema](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|Utente non abilitato per SIP  <br/> |Se per l'organizzazione è disponibile un'installazione precedente di Microsoft Office Communications Server o Microsoft Lync Server 2010, è possibile che gli utenti non siano stati eliminati dal server prima di rimuoverne le autorizzazioni. Di conseguenza l'attributo **msRTCSIP-UserEnabled** è ancora impostato su **FALSE** in Servizi di Dominio di Active Directory. <br/> |[Aggiornare le impostazioni utente in Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>Aggiungere una voce del firewall per msoidsvc.exe al server proxy
<a name="add-a-firewall"> </a>

Questa procedura è una possibile soluzione per il messaggio di errore seguente: **Indirizzo di accesso non trovato**.

> [!NOTE]
> Le seguenti operazioni presuppongono l’utilizzo di Microsoft Forefront Threat Management Gateway (TMG) 2010. Se si dispone di una diversa soluzione a gateway web, usare le impostazioni descritte nel passaggio 4.


Per creare una voce per l'applicazione Msoidsvc.exe in Forefront TMG 2010, eseguire le operazioni seguenti:

1. Nel riquadro sinistro di Forefront fare clic su **Networking**.

2. Fare clic sulla scheda **Network**. Nella scheda **Tasks** del riquadro destro fare clic su **Configure Forefront TMG Client Settings**.

3. Nella finestra di dialogo **Forefront TMG Client Settings** fare clic su **New**.

4. Nella finestra di dialogo **Application Entry Setting** configurare le regole seguenti:

|**Applicazione**|**Chiave**|**Valore**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Disabilita  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

Per informazioni dettagliate, vedere l'articolo della Microsoft Knowledge Base 2409256 [Non è possibile connettersi a Skype for Business online perché un firewall locale blocca la connessione](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).

### <a name="update-dns-settings"></a>Aggiornare le impostazioni DNS
<a name="update-dns-service"> </a>

Se l'organizzazione dispone di un dominio personalizzato, questa procedura è una possibile soluzione per il messaggio di errore seguente: **Server temporaneamente non disponibile**.

- Contattare il registrar per informazioni su come aggiungere il record CNAME seguente al dominio:

  - **Tipo di record DNS**: CNAME

  - **Nome**: sip

  - **Valore/Destinazione**: sipdir.online.lync.com

Per informazioni dettagliate, vedere l'articolo della Microsoft Knowledge Base 2566790, [Risoluzione dei problemi di Skype for Business online per problemi di configurazione di DNS in Office 365](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>Installare un certificato SSL di terze parti nel server ADFS
<a name="verify-upn-and"> </a>

Per installare un certificato SSL di terze parti nel server Active Domain Federation Services (ADFS), eseguire le operazioni seguenti:

1. Ottenere un certificato SSL da un'Autorità di certificazione di terze parti come VeriSign o Thawte.

2. Installare il certificato nel server ADFS con la console di gestione di Active Directory Federation Services.

### <a name="update-security-credentials"></a>Aggiornare le credenziali di sicurezza
<a name="update-security-credentials"> </a>

Questa procedura è una possibile soluzione per il messaggio di errore **Si è verificato un problema durante l'acquisizione di un certificato personale richiesto per eseguire l'accesso**.

Per eliminare possibili problemi di certificato o credenziali, rinnovare prima di tutto il certificato dell'utente in Gestione certificati Windows. A tale scopo, eseguire la procedura seguente:

1. Aprire Windows Certificate Manager. A questo scopo, fare clic su **Start**, scegliere **Esegui**, digitare **certmgr.msc**, quindi fare clic su **OK**.

2. Fare doppio clic su **Personali** e quindi fare doppio clic su **Certificati**.

3. Ordinare le informazioni in base alla colonna **Emesso da** e quindi cercare un certificato emesso da Communications Server.

4. Fare clic con il pulsante destro del mouse sul certificato e quindi scegliere **Elimina**.

In seguito, se l'utente esegue Windows 7, rimuovere le credenziali archiviate in Gestione credenziali in Windows Credential Manager. A tale scopo, eseguire la procedura seguente:

1. Fare clic sul pulsante **Start**, scegliere **Pannello di controllo** e quindi fare clic su **Gestione credenziali**.

2. Individuare il set di credenziali usato per la connessione a Skype for Business online.

3. Espandere il set di credenziali e quindi fare clic su **Rimuovi dall'insieme di credenziali**.

4. Effettuare nuovamente l’accesso e reimmettere le credenziali dell'utente.

Infine, se l'utente non riesce ancora ad accedere dopo l'aggiornamento delle credenziali, provare a eliminare la cartella RSA nel computer dell'utente, perché potrebbe impedire il completamento del processo di autenticazione dell'utente:

1. Accedere al computer dell'utente con un account di amministratore.

2. Se necessario, attivare l'opzione di visualizzazione della cartella **Visualizzare i file nascosti**.

3. Digitare il percorso seguente nella barra degli indirizzi di Esplora File: **C:\\Documents and Settings\\NomeUtente\\Application Data\\Microsoft\\Crypto\\RSA**, dove***NomeUtente*** è il nome di accesso di Windows.

4. Eliminare le eventuali cartelle con un nome che inizia con **S-1-5-21-** seguito da una stringa di numeri.

### <a name="modify-trustmodeldata-registry-keys"></a>Modificare le chiavi TrustModelData del Registro di sistema
<a name="modify-trustmodeldata-registry"> </a>

Quando un utente accede per la prima volta, potrebbe comparire una finestra di dialogo contenente il seguente avviso: **Impossibile verificare che il server sia attendibile per l'indirizzo di accesso. Connettersi comunque?** Questa è una funzionalità di sicurezza e non un messaggio di errore. Tuttavia, è possibile impedire la comparsa della finestra di dialogo usando un Oggetto Criteri di gruppo (GPO) per aggiornare il computer degli utenti con il proprio nome di dominio prima di accedere per la prima volta. A tale scopo, effettuare le seguenti operazioni:

- Creare e distribuire un oggetto Criteri di gruppo che aggiunga il nome di dominio Skype for Business, ad esempio nomeDominio.contoso.com, al valore corrente di HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData.

> [!IMPORTANT]
>  È necessario *aggiungere* il proprio nome di dominio al valore esistente e non sostituirlo semplicemente.

Per informazioni dettagliate, vedere l'articolo 2531068 della Microsoft Knowledge Base [Skype for Business (Lync) non riesce a verificare che il server sia attendibile per l'indirizzo di accesso](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).

### <a name="update-user-settings-in-active-directory"></a>Caricare le impostazioni dell'utente in Active Directory
<a name="update-user-settings"> </a>

Se per l'organizzazione è disponibile un'installazione precedente di Microsoft Office Communications Server o Microsoft Lync Server 2010, è possibile che gli utenti non siano stati eliminati dal server prima di rimuoverne le autorizzazioni. Di conseguenza l'attributo **msRTCSIP-UserEnabled** è ancora impostato su **FALSE** in Servizi di Dominio di Active Directory.

Per risolvere il problema, eseguire le operazioni seguenti:

1. Aggiornare l'attributo **msRTCSIP-UserEnabled** per tutti gli utenti interessati, impostandolo su **TRUE**.

2. Eseguire nuovamente lo Strumento di sincronizzazione della directory dei Microsoft Online Services. Per informazioni dettagliate, vedere [AIntegrate locale directory con Azure Active Directory](https://technet.microsoft.com/it-IT/library/hh967642.aspx).

Per risolvere i problemi di accesso a Skype for Business online problemi, è bene iniziare eliminando le cause più comuni dei problemi di accesso. Se necessario, è possibile seguire una procedura di risoluzione specifica in base al tipo di errore. Se non è ancora possibile accedere, raccogliere nuove informazioni e chiedere ulteriore assistenza.
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Usare la guida alla risoluzione dei problemi del supporto tecnico Microsoft
<a name="toc325626447"> </a>

Se non si riesce ancora a risolvere i problemi di accesso dell'utente, esaminare i suggerimenti descritti nell'articolo 2541980 della Microsoft Knowledge Base [Come risolvere i problemi di autenticazione e connettività in Skype for Business online](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).

## <a name="collect-more-information-and-seek-additional-help"></a>Raccogliere ulteriori informazioni e richiedere assistenza
<a name="collect-more-information"> </a>

Se dopo aver seguito le istruzioni nelle sezioni precedenti non è ancora possibile risolvere i problemi di accesso, è necessario raccogliere ulteriori informazioni e contattare il supporto tecnico.  A tale scopo, eseguire la procedura seguente:

1. Ottenere i file di log e i dettagli registro eventi di Windows dal computer dell'utente. Per istruzioni dettagliate, vedere l'argomento della Guida dell’utente finale [Attivare a registrazione eventi in Lync](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).

2. Inviare al supporto tecnico Microsoft i file di registrazione e le informazioni dettagliate sull'errore.

Potrebbero essere richieste ulteriori informazioni diagnostiche installando il Toolkit di supporto Microsoft Online Services Diagnostics and Logging (MOSDAL) nel computer dell'utente interessato.  Per ulteriori informazioni, vedere [Uso del Toolkit di supporto MOSDAL](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).

Per risolvere i problemi di accesso a Skype for Business online problemi, è bene iniziare eliminando le cause più comuni dei problemi di accesso. Se necessario, è possibile seguire una procedura di risoluzione specifica in base al tipo di errore. Se non è ancora possibile accedere, raccogliere nuove informazioni e chiedere ulteriore assistenza.

## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)


