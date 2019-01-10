---
title: Risoluzione dei problemi Skype per errori di accesso Business Online per amministratori
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Ulteriori cause più comuni per Skype per errori di accesso Business Online e lavoro e risoluzione dei problemi relativi a tali problemi. '
ms.openlocfilehash: b9eccd817fbb9a67fcbce61d73b4a701c6b063de
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789085"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>Risoluzione dei problemi Skype per errori di accesso Business Online per amministratori

Per risolvere i problemi Skype per errori di accesso Business Online, avviare eliminando le cause più comuni di accesso difficoltà. Se necessario, è possibile seguire quindi risoluzione specifica passaggi in base al tipo di errore. Se l'utente di accesso persiste, raccogliere le informazioni aggiuntive e quindi cercare informazioni aggiuntive.

## <a name="what-do-you-want-to-do"></a>Per saperne di più
<a name="top"> </a>

> [Controllare le cause comuni di Skype per errori di accesso Business Online](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
> 
> [Eseguire passaggi di risoluzione per uno specifico errore (solo Enterprise)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
> 
> [Aggiungere una voce del firewall per msoidsvc.exe al server proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
> 
> [Aggiornare le impostazioni DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
> 
> [Installare un certificato SSL di terze parti nel server ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
> 
> [Aggiornare le credenziali di protezione](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
> 
> [Modificare chiavi del Registro di sistema TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
> 
> [Aggiornare le impostazioni utente in Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
> 
> [Utilizzare il supporto di Microsoft risoluzione dei problemi di Guida](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
> 
> [Raccogliere ulteriori informazioni e seek avere ulteriore assistenza](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Controllare le cause comuni di Skype per errori di accesso Business Online
<a name="toc323194094"> </a>

La maggior parte dei problemi di accesso possono essere registrati per un numero limitato di cause e molte di queste sono facili da correggere. Nella tabella seguente sono elencati alcuni cause più comuni di errori di accesso e alcuni passaggi che si o gli utenti possono essere eseguite per risolverli.


| **Possibili Cause**                                                                                                                                                    | **Soluzione**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Durante l'accesso, viene visualizzata una finestra di dialogo che contiene la frase seguente: **non possono verificare che il server sia attendibile per l'indirizzo di accesso. Connettersi comunque?** <br/> | Verificare che il nome di dominio nella finestra di dialogo è un server trusted nell'organizzazione, ad esempio **domainName.contoso.com**. Chiedere all'utente di selezionare la casella di controllo **sempre considerare attendibile il server** e quindi fare clic su **Connetti**. <br/> I clienti aziendali possono viene impedita questo messaggio quando un utente accede per la prima volta, modificando il Registro di sistema nel computer di ogni utente. Per ulteriori informazioni, vedere [chiavi del Registro di sistema TrustModelData modificare](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).<br/> |
| Indirizzo di accesso errata, nome utente o password  <br/>                                                                                                               | Verificare che il nome di accesso e la password dell'utente siano corretti. <br/>  Verificare che il nome dell'utente accesso viene formattato come indicato di seguito: <strong>bobk@contoso.com</strong>. Potrebbe essere diverso dal formato da utilizzare per l'accesso alla rete dell'organizzazione.  <br/>  Chiedere all'utente di provare a effettuare nuovamente l'accesso. <br/>                                                                                                                                                                                                                             |
| Password dimenticata  <br/>                                                                                                                                             | Reimpostare la password dell'utente e notificare all'utente la nuova password temporanea.  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Non è consentito per utilizzare Skype Business online  <br/>                                                                                                                  | Verificare che l'utente è registrato come Skype per utenti Business Online. In caso contrario, registrare l'utente e quindi chiedere all'utente di effettuare nuovamente l'accesso.  <br/>                                                                                                                                                                                                                                                                                                                                                                                           |
| Versione corretta di Skype Business online installato  <br/>                                                                                                           | Questo problema è in genere associato a un messaggio di errore contenente il messaggio seguente: **il servizio di autenticazione non è compatibile con questa versione del programma**.  <br/> Chiedere all'utente di disinstallare e reinstallare Skype per Business Online dal portale di Office 365.  <br/>                                                                                                                                                                                                                                                    |
| Acquisizione di un certificato personale che è necessario che tu acceda problema  <br/>                                                                                           | Se recentemente è stato modificato indirizzo di accesso dell'utente, potrebbe essere necessario eliminare i dati memorizzati nella cache accesso. Chiedere agli utenti di disconnessione, fare clic su Elimina collegamento nella schermata di accesso personale informazioni di accesso e quindi riprovare.  <br/>                                                                                                                                                                                                                                                                                                                                |
| Impostare un nome di dominio personalizzato e le modifiche potrebbero non aver completato la propagazione nel sistema.  <br/>                                                         | Per prima cosa, verificare che sia stata modificata i record del servizio DNS (Domain Name) in modo da riflettere le modifiche.  <br/> Se sono state già le modifiche necessarie DNS, consigliare all'utente di prova registrazione in seguito. Le modifiche al DNS possono richiedere fino a 72 ore per rendere effettive in tutto il sistema.  <br/>                                                                                                                                                                                                                                                        |
| Sistema di clock non è sincronizzata con orologio del server  <br/>                                                                                                                     | Verificare che il controller di dominio di rete la sincronizzazione con un'origine esterna affidabile. Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base 816042 della [procedura configurare un server di riferimento ora autorevole in Windows Server](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).<br/>                                                                                                                                                                                                                                          |

Per risolvere i problemi Skype per errori di accesso Business Online, avviare eliminando le cause più comuni di accesso difficoltà. Se necessario, è possibile seguire quindi risoluzione specifica passaggi in base al tipo di errore. Se l'utente di accesso persiste, raccogliere le informazioni aggiuntive e quindi cercare informazioni aggiuntive.

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>Eseguire passaggi di risoluzione per uno specifico errore (solo Enterprise)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  In queste istruzioni sono destinate principalmente per i clienti E pianificazione di Microsoft Office 365. Se si è un cliente di Office 365 pianificare P, continuare con la sezione seguente,[raccogliere ulteriori informazioni e seek avere ulteriore assistenza ](troubleshooting-sign-in-errors-for-admins.md#collect-more-information).

Se l'utente non può effettuare l'accesso dopo avere tentato i suggerimenti nella sezione precedente, è possibile eseguire ulteriori la risoluzione dei problemi in base al tipo di errore. Nella tabella seguente sono elencati i messaggi di errore più comuni e le possibili cause. Nella tabella seguente sono le procedure dettagliate per risolvere i problemi.

|**Messaggio di errore**|**Possibili cause**|**Soluzione**|
|:-----|:-----|:-----|
|Indirizzo di accesso non trovato  <br/> |Le richieste di accesso dall'Assistente Microsoft Online Services Sign-On (msoidsvc.exe) non verranno attraverso il firewall esterno o server proxy.  <br/> |[Aggiungere una voce del firewall per msoidsvc.exe al server proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|Server è temporaneamente non disponibile  <br/> |Se l'organizzazione dispone di un dominio personalizzato, le impostazioni necessarie del sistema DNS (Domain Name) potrebbero essere mancanti o errati.  <br/> |[Aggiornare le impostazioni DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|Server è temporaneamente non disponibile  <br/> |Se l'organizzazione utilizza single sign-on con Active Directory Federation Services (ADFS), è stata utilizzata un certificato autofirmato Secure Socket Layer (SSL) anziché uno da un'autorità di certificazione di terze parti.  <br/> |[Installare un certificato SSL di terze parti nel server ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|Acquisizione di un certificato personale che è necessario che tu acceda problema  <br/> |Se è già stato rimosso i dati memorizzati nella cache server utilizzati per l'accesso e l'errore viene nuovamente visualizzato, le credenziali di protezione dell'utente è danneggiate o una cartella RSA nel computer dell'utente può determinare il blocco di autenticazione.  <br/> |[Aggiornare le credenziali di protezione](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|Quando un utente accede per la prima volta, verrà visualizzata una finestra di dialogo certificato relazione di trust.  <br/> |Questa finestra di dialogo viene visualizzato se il Skype per Business server non è ancora elencato nella chiave del Registro di sistema **TrustModelData** . <br/> |[Modificare chiavi del Registro di sistema TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|Utenti non sono abilitati per SIP  <br/> |Se l'organizzazione dispone di un'installazione di Microsoft Office Communications Server o Microsoft Lync Server 2010, si potrebbero non essere eliminato gli utenti dal server prima della rimozione delle autorizzazioni. Di conseguenza, l'attributo **msRTCSIP-UserEnabled** ancora è impostato su **FALSE** in servizi di dominio Active Directory. <br/> |[Aggiornare le impostazioni utente in Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>Aggiungere una voce del firewall per msoidsvc.exe al server proxy
<a name="add-a-firewall"> </a>

Questa procedura è possibile correzione per il messaggio di errore: **indirizzo di accesso non viene trovato**.

> [!NOTE]
> I passaggi seguenti presuppongono che l'utilizzo di Microsoft Forefront Threat Management Gateway (TMG) 2010. Se si dispone di una soluzione gateway web diversa, utilizzare le impostazioni descritte nel passaggio 4 di seguito.


Per creare una voce di applicazione per Msoidsvc.exe in Forefront TMG 2010, procedere come segue:

1. Nel riquadro sinistro Forefront, fare clic su **rete**.

2. Fare clic sulla scheda di **rete** . Nella scheda **attività** nel riquadro destro fare clic su **Configura impostazioni di Forefront TMG Client**.

3. Nella finestra di dialogo **Impostazioni del Client di Forefront TMG** fare clic su **Nuovo**.

4. Nella finestra di dialogo **Impostazione delle voci di applicazione** , configurare le regole seguenti:

|**Applicazione**|**Chiave**|**Valore**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Disabilitare  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base 2409256, [che è possibile connettersi a Skype Business online poiché un firewall locale blocca la connessione](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).

### <a name="update-dns-settings"></a>Aggiornare le impostazioni DNS
<a name="update-dns-service"> </a>

Se l'organizzazione dispone di un dominio personalizzato, questa procedura è possibile correzione per il messaggio di errore: **Server è temporaneamente non disponibile**.

- Per informazioni su come aggiungere il seguente record CNAME per il dominio, contattare il registrar nome:

  - **Tipo di record DNS**: CNAME

  - **Nome**: sip

  - **Valore/destinazione**: sipdir.online.lync.com

Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base 2566790, [Risoluzione dei problemi Skype per problemi di configurazione di DNS Online Business in Office 365](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>Installare un certificato SSL di terze parti nel server ADFS
<a name="verify-upn-and"> </a>

Per installare un certificato SSL di terze parti nel server attivo dominio Federation Services (ADFS), eseguire la procedura seguente:

1. Ottenere un certificato SSL da un'autorità di certificazione di terze parti, ad esempio VeriSign o Thawte.

2. Installare il certificato nel server ADFS utilizzando la console di gestione ADFS.

### <a name="update-security-credentials"></a>Aggiornare le credenziali di protezione
<a name="update-security-credentials"> </a>

Questa procedura è possibile correzione per il messaggio di errore **problema acquisto di un certificato personale richiesto per l'accesso**.

Per eliminare i possibili problemi di certificato o credenziali, rinnovare innanzitutto il certificato dell'utente in Gestione certificati di Windows. A tale scopo, eseguire la procedura seguente:

1. Aprire Gestione certificati di Windows. A tale scopo, fare clic su **Start**, scegliere **Esegui**, digitare **certmgr. msc**e quindi fare clic su **OK**.

2. Fare doppio clic su **personale**e quindi fare doppio clic su **certificati**.

3. Ordina per la colonna **Rilasciato da** e quindi cercare un certificato emesso da Communications Server.

4. Destro del mouse sul certificato e quindi fare clic su **Elimina**.

Successivamente, se l'utente è in esecuzione Windows 7, rimuovere le proprie credenziali memorizzate in Gestione credenziali di Windows. A tale scopo, eseguire la procedura seguente:

1. Fare clic su **Start**, scegliere **Pannello di controllo**e quindi fare clic su **Gestione credenziali**.

2. Individuare il set di credenziali che viene utilizzato per connettersi a Skype Business online.

3. Espandere il set di credenziali e quindi fare clic su **Rimuovi dall'insieme di credenziali**.

4. Eseguire nuovamente l'accesso e immettere nuovamente le credenziali dell'utente.

Infine, se l'utente di accesso persiste dopo aver aggiornato le proprie credenziali, provare a eseguire l'eliminazione della cartella RSA nel computer dell'utente, poiché è Impossibile impedisca il completamento del processo di autenticazione utente:

1. Accedere al computer dell'utente utilizzando un account di amministratore.

2. Se necessario, attivare l'opzione di visualizzazione di cartella **Mostra file nascosti**.

3. Digitare il comando seguente nella barra degli indirizzi del File Explorer: **c:\\Documents and Settings\\UserName\\dati delle applicazioni\\Microsoft\\crittografia\\RSA**, dove ***il nome utente*** è il nome di accesso di Windows.

4. Eliminare qualsiasi cartella che inizia con il nome **S-1-5-21 -** seguita da una stringa di numeri.

### <a name="modify-trustmodeldata-registry-keys"></a>Modificare chiavi del Registro di sistema TrustModelData
<a name="modify-trustmodeldata-registry"> </a>

Quando un utente accede per la prima volta, può ricevere una finestra di dialogo che contiene un elemento analogo al seguente: **non possono verificare che il server sia attendibile per l'indirizzo di accesso. Connettersi comunque?** Questa è una funzionalità di sicurezza e non un errore. Tuttavia, è possibile viene impedita la finestra di dialogo utilizzando un oggetto Criteri di gruppo (GPO) per aggiornare i computer degli utenti con il nome di dominio prima di accesso per la prima volta. A tale scopo, eseguire le operazioni seguenti:

- Creare e distribuire un oggetto Criteri di gruppo che aggiunge il Skype per nome di dominio aziendale, ovvero domainName.contoso.com—to, ad esempio, il valore corrente del HKEY_LOCAL_MACHINE\\Software\\criteri\\Microsoft\\Communicator\\ TrustModelData.

> [!IMPORTANT]
>  È necessario *aggiungere* il nome di dominio per il valore esistente, non semplicemente lo sostituisce.

Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base 2531068, [che Skype per le aziende (Lync) non può verificare che il server sia attendibile per l'indirizzo di accesso](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).

### <a name="update-user-settings-in-active-directory"></a>Aggiornare le impostazioni utente in Active Directory
<a name="update-user-settings"> </a>

Se l'organizzazione dispone di un'installazione di Microsoft Office Communications Server o Microsoft Lync Server 2010, si potrebbero non essere eliminato gli utenti dal server prima della rimozione delle autorizzazioni. Di conseguenza, l'attributo **msRTCSIP-UserEnabled** ancora è impostato su **FALSE** in servizi di dominio Active Directory.

Per risolvere questo problema, eseguire la procedura seguente:

1. Aggiornare l'attributo **msRTCSIP-UserEnabled** per tutti gli utenti interessati su **TRUE**.

2. Eseguire di nuovo lo strumento di sincronizzazione Directory di Microsoft Online Services (DirSync). Per ulteriori informazioni, vedere [Directory AIntegrate locale con Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx).

Per risolvere i problemi Skype per errori di accesso Business Online, avviare eliminando le cause più comuni di accesso difficoltà. Se necessario, è possibile seguire quindi risoluzione specifica passaggi in base al tipo di errore. Se l'utente di accesso persiste, raccogliere le informazioni aggiuntive e quindi cercare informazioni aggiuntive.
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Utilizzare il supporto di Microsoft risoluzione dei problemi di Guida
<a name="toc325626447"> </a>

Se si è ancora non in grado di risolvere i problemi di accesso dell'utente, esaminare i suggerimenti nell'articolo della Microsoft Knowledge Base 2541980, [come per la risoluzione dei problemi di accesso in Skype Business online](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).

## <a name="collect-more-information-and-seek-additional-help"></a>Raccogliere ulteriori informazioni e seek avere ulteriore assistenza
<a name="collect-more-information"> </a>

Se si aver effettuato le istruzioni precedenti e ancora non è in grado di risolvere i problemi di accesso, è necessario raccogliere le informazioni aggiuntive e contattare il supporto tecnico. A tale scopo, eseguire la procedura seguente:

1. Ottenere il file di registro e i dettagli del registro eventi di Windows dal computer dell'utente. Per istruzioni dettagliate, vedere l'argomento della Guida dell'utente finale [attivare i log degli errori in Lync](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).

2. Inviare il file di registro e informazioni dettagliate sull'errore per il supporto tecnico Microsoft.

Potrebbe essere necessario fornire ulteriori informazioni di diagnostica per l'installazione di Microsoft Online Services diagnostica e Toolkit di supporto Logging (MOSDAL) nel computer dell'utente interessato. Per ulteriori informazioni, vedere [utilizzo Toolkit di supporto](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).

Per risolvere i problemi Skype per errori di accesso Business Online, avviare eliminando le cause più comuni di accesso difficoltà. Se necessario, è possibile seguire quindi risoluzione specifica passaggi in base al tipo di errore. Se l'utente di accesso persiste, raccogliere le informazioni aggiuntive e quindi cercare informazioni aggiuntive.

## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)


