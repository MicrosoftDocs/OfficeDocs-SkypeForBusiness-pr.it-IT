---
title: Gestire l'autenticazione a due fattori in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: "Riepilogo: gestire l'autenticazione a due fattori in Skype for Business Server."
ms.openlocfilehash: 415eb23779450bc09cdaa25ea2e60b6cf3526e40
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806542"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Gestire l'autenticazione a due fattori in Skype for Business Server
 
**Riepilogo:** Gestire l'autenticazione a due fattori in Skype for Business Server.
  
L'autenticazione a due fattori offre una maggiore sicurezza richiedendo agli utenti di fornire due forme di autenticazione o identificazione, una combinazione nome utente/password e token o certificato. Questa operazione è nota anche come "qualcosa di cui si dispone, qualcosa che si conosce". 
  
Un esempio tipico di autenticazione a due fattori con un certificato è l'uso di smart card. Una smart card contiene un certificato associato all'account utente e può essere convalidata in base alle informazioni sull'utente e sul certificato archiviate in un server. Confrontando le informazioni utente (nome utente e password) con il certificato fornito, il server convalida le credenziali e autentica l'utente.
  
Quando si configura un ambiente Skype for Business Server per supportare l'autenticazione a due fattori, considerare gli argomenti seguenti.
  
## <a name="client-support"></a>Supporto client

Gli aggiornamenti cumulativi per lync Server 2013: client desktop di luglio 2013 e il client Skype for Business sono gli unici client che attualmente supportano l'autenticazione a due fattori.
  
## <a name="topology-requirements"></a>Requisiti della topologia

I clienti sono invitati a distribuire l'autenticazione a due fattori usando Skype for Business Server dedicato con pool di server perimetrali, director e utenti. Per abilitare l'autenticazione passiva per gli utenti, è necessario disabilitare altri metodi di autenticazione per altri ruoli e servizi, tra cui:
  
|**Tipo di configurazione**|**Tipo di servizio**|**Ruolo del server**|**Tipo di autenticazione da disabilitare**|
|:-----|:-----|:-----|:-----|
|Web Service  <br/> |WebServer  <br/> |Direttore  <br/> |Kerberos, NTLM e certificato  <br/> |
|Web Service  <br/> |WebServer  <br/> |Front End  <br/> |Kerberos, NTLM e certificato  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos e NTLM  <br/> |
|Proxy  <br/> |Registrar  <br/> |Front End  <br/> |Kerberos e NTLM  <br/> |
   
A meno che questi tipi di autenticazione non siano disabilitati a livello di servizio, tutte le altre versioni del client non saranno in grado di accedere correttamente una volta abilitata l'autenticazione a due fattori all'interno della distribuzione.
  
## <a name="skype-for-business-service-discovery"></a>Individuazione dei servizi di Skype for Business

I record DNS utilizzati dai client interni ed/o esterni per individuare i servizi Skype for Business devono essere configurati per la risoluzione in un server Skype for Business non abilitato per l'autenticazione a due fattori. Con questa configurazione, gli utenti dei pool Skype for Business non abilitati per l'autenticazione a due fattori non saranno tenuti a immettere un PIN per l'autenticazione, mentre gli utenti dei pool Skype for Business abilitati per l'autenticazione a due fattori saranno necessari per immettere il PIN per l'autenticazione.
  
## <a name="exchange-authentication"></a>Autenticazione di Exchange

I clienti che hanno distribuito l'autenticazione a due fattori per Microsoft Exchange potrebbero scoprire che alcune funzionalità nel client non sono disponibili. Questo è attualmente da progettazione, poiché il client Skype for Business non supporta l'autenticazione a due fattori per le funzionalità che dipendono dall'integrazione di Exchange.
  
## <a name="contacts"></a>Contatti

Gli utenti di Skype for Business configurati per sfruttare la funzionalità Archivio contatti unificato scopriranno che i loro contatti non sono più disponibili dopo l'accesso con l'autenticazione a due fattori.
  
È consigliabile utilizzare il cmdlet **Invoke-CsUcsRollback** per rimuovere i contatti utente esistenti dall'archivio contatti unificato e archiviarli in Skype for Business Server prima di abilitare l'autenticazione a due fattori.
  
## <a name="skill-search"></a>Ricerca competenze

I clienti che hanno configurato la funzionalità Di ricerca per competenza nell'ambiente Skype for Business scopriranno che questa funzionalità non funziona quando Skype for Business è abilitato per l'autenticazione a due fattori. Questo è da progettazione, poiché Microsoft SharePoint attualmente non supporta l'autenticazione a due fattori.
  
## <a name="credentials"></a>Credentials

Esistono alcune considerazioni sulla distribuzione che riguardano le credenziali di Skype for Business salvate che possono influire sugli utenti configurati per l'utilizzo dell'autenticazione a due fattori.
  
### <a name="deleting-saved-credentials"></a>Eliminazione delle credenziali salvate

Gli utenti  devono usare l'opzione Elimina le informazioni di accesso nel client Skype for Business ed eliminare la cartella del profilo SIP da %localappdata%\Microsoft\Office\15.0\Skype for Business prima di tentare di accedere per la prima volta utilizzando l'autenticazione a due fattori.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Con il metodo di autenticazione Kerberos o NTLM, le credenziali di Windows dell'utente vengono utilizzate automaticamente per l'autenticazione. In una distribuzione tipica di Skype for Business Server in cui Kerberos e/o NTLM è abilitato per l'autenticazione, gli utenti non devono immettere le proprie credenziali ogni volta che eseguono l'accesso.
  
Se agli utenti vengono involontariamente richieste le credenziali prima che venga richiesto di immettere il PIN, la chiave del Registro di sistema **DisableNTCredentials** potrebbe essere configurata involontariamente nei computer client, probabilmente tramite Criteri di gruppo.
  
Per impedire la richiesta aggiuntiva di credenziali, creare la seguente voce del Registro di sistema nella workstation locale o utilizzare il modello amministrativo di Skype for Business da applicare a tutti gli utenti per un determinato pool tramite Criteri di gruppo:
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Quando un utente accede a Skype for Business per la prima volta, all'utente viene richiesto di salvare la password. Se selezionata, questa opzione consente di archiviare il certificato client dell'utente nell'archivio certificati personali e le credenziali di Windows dell'utente in Gestione credenziali del computer locale.
  
L'impostazione del Registro di sistema **SavePassword** deve essere disabilitata quando Skype for Business è configurato per supportare l'autenticazione a due fattori. Per impedire agli utenti di salvare le password, modificare la seguente voce del Registro di sistema nella workstation locale o utilizzare il modello amministrativo di Skype for Business da applicare a tutti gli utenti di un determinato pool tramite Criteri di gruppo:
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>Riesecuzione token AD FS 2.0

ADFS 2.0 offre una funzionalità denominata rilevamento della riproduzione di token, in base alla quale è possibile rilevare e quindi eliminare più richieste di token che usano lo stesso token. Quando questa funzionalità è abilitata, il rilevamento della riproduzione dei token protegge l'integrità delle richieste di autenticazione sia nel profilo passivo di WS-Federation che nel profilo WebSSO SAML assicurando che lo stesso token non sia mai utilizzato più di una volta.
  
Questa funzionalità deve essere abilitata in situazioni in cui la sicurezza è molto importante, ad esempio quando si usano chioschi. Per ulteriori informazioni sul rilevamento della riproduzione di token, vedere Procedure consigliate per la pianificazione e [la distribuzione sicure di ADFS 2.0.](https://go.microsoft.com/fwlink/p/?LinkId=309215)
  
## <a name="external-user-access"></a>Accesso utente esterno

La configurazione di un proxy ADFS o di un proxy inverso per supportare l'autenticazione a due fattori di Skype for Business da reti esterne non è trattata in questi argomenti.
  
## <a name="see-also"></a>Vedere anche

[Configurare l'autenticazione a due fattori in Skype for Business Server](configure-two-factor.md)
  
