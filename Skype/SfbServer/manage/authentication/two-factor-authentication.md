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
  
L'autenticazione a due fattori garantisce una maggiore sicurezza richiedendo agli utenti di fornire due forme di autenticazione o identificazione, ovvero una combinazione di nome utente/password e un token o un certificato. Questo è conosciuto anche come "qualcosa che hai, qualcosa che conosci". 
  
Un esempio tipico di autenticazione a due fattori con un certificato è l'utilizzo delle smart card. Una smart card contiene un certificato associato all'account utente e può essere convalidato in base alle informazioni sugli utenti e sui certificati archiviati in un server. Confrontando le informazioni utente (nome utente e password) per il certificato fornito, il server convalida le credenziali e autentica l'utente.
  
Si consideri gli argomenti seguenti quando si configura un ambiente di Skype for Business Server per supportare l'autenticazione a due fattori.
  
## <a name="client-support"></a>Supporto client

Gli aggiornamenti cumulativi per Lync Server 2013: client desktop di luglio 2013 e il client Skype for business sono gli unici client che attualmente supportano l'autenticazione a due fattori.
  
## <a name="topology-requirements"></a>Requisiti della topologia

I clienti sono fortemente incoraggiati a distribuire l'autenticazione a due fattori utilizzando Skype for Business Server dedicato con pool di Edge, Director e User. Per abilitare l'autenticazione passiva per gli utenti, altri metodi di autenticazione devono essere disattivati per altri ruoli e servizi, tra cui i seguenti:
  
|**Tipo di configurazione**|**Tipo di servizio**|**Ruolo del server**|**Tipo di autenticazione da disabilitare**|
|:-----|:-----|:-----|:-----|
|Web Service  <br/> |WebServer  <br/> |Direttore  <br/> |Kerberos, NTLM e certificato  <br/> |
|Web Service  <br/> |WebServer  <br/> |Front End  <br/> |Kerberos, NTLM e certificato  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos e NTLM  <br/> |
|Proxy  <br/> |Registrar  <br/> |Front End  <br/> |Kerberos e NTLM  <br/> |
   
A meno che questi tipi di autenticazione non siano disabilitati a livello di servizio, tutte le altre versioni del client non saranno in grado di accedere correttamente dopo che è stata abilitata l'autenticazione a due fattori all'interno della distribuzione.
  
## <a name="skype-for-business-service-discovery"></a>Individuazione del servizio Skype for business

I record DNS utilizzati dai client interni e/o esterni per individuare i servizi Skype for business devono essere configurati in modo da essere risolti in un server Skype for business non abilitato per l'autenticazione a due fattori. Con questa configurazione, gli utenti di pool Skype for business che non sono abilitati per l'autenticazione a due fattori non devono immettere un PIN da autenticare, mentre gli utenti dei pool Skype for business abilitati per l'autenticazione a due fattori saranno tenuti a immettere il proprio PIN da autenticare.
  
## <a name="exchange-authentication"></a>Autenticazione di Exchange

I clienti che hanno distribuito l'autenticazione a due fattori per Microsoft Exchange possono rilevare che alcune caratteristiche nel client non sono disponibili. Questo è attualmente in fase di progettazione, in quanto il client Skype for business non supporta l'autenticazione a due fattori per le caratteristiche che dipendono dall'integrazione di Exchange.
  
## <a name="contacts"></a>Contatti

Gli utenti di Skype for business che sono configurati per sfruttare la caratteristica archivio contatti unificato troveranno che i loro contatti non sono più disponibili dopo aver eseguito l'accesso con l'autenticazione a due fattori.
  
È consigliabile utilizzare il cmdlet **Invoke-CsUcsRollback** per rimuovere i contatti utente esistenti dall'archivio contatti unificato e archiviarli in Skype for Business Server prima di abilitare l'autenticazione a due fattori.
  
## <a name="skill-search"></a>Ricerca skill

I clienti che hanno configurato la funzionalità di ricerca Skill nell'ambiente Skype for business troveranno che questa funzionalità non funziona quando Skype for business è abilitato per l'autenticazione a due fattori. Questo è in base alla progettazione, in quanto Microsoft SharePoint attualmente non supporta l'autenticazione a due fattori.
  
## <a name="credentials"></a>Credentials

Sono presenti diverse considerazioni sulla distribuzione che coinvolgono le credenziali salvate di Skype for business, che potrebbero influire sugli utenti configurati per l'utilizzo dell'autenticazione a due fattori.
  
### <a name="deleting-saved-credentials"></a>Eliminazione delle credenziali salvate

Gli utenti devono utilizzare l'opzione **delete my Sign-in info** nel client Skype for business ed eliminare la cartella del profilo SIP da%LocalAppData%\Microsoft\Office\15.0\Skype for business prima di tentare di firmare per la prima volta utilizzando l'autenticazione a due fattori.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Con il metodo di autenticazione Kerberos o NTLM, le credenziali di Windows dell'utente vengono utilizzate automaticamente per l'autenticazione. In una tipica distribuzione di Skype for Business Server in cui Kerberos e/o NTLM è abilitato per l'autenticazione, gli utenti non devono immettere le proprie credenziali ogni volta che accedono.
  
Se agli utenti vengono richieste involontariamente le credenziali prima che venga richiesto di immettere il proprio PIN, la chiave del registro di sistema **DisableNTCredentials** potrebbe essere involontariamente configurata nei computer client, possibilmente tramite criteri di gruppo.
  
Per impedire la richiesta aggiuntiva di credenziali, creare la seguente voce del registro di sistema nella workstation locale o utilizzare il modello amministrativo Skype for business da applicare a tutti gli utenti di un determinato pool utilizzando criteri di gruppo:
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Quando un utente accede a Skype for business per la prima volta, all'utente viene richiesto di salvare la propria password. Se selezionata, questa opzione consente di archiviare il certificato client dell'utente nell'archivio certificati personale e le credenziali di Windows dell'utente da archiviare in Gestione credenziali del computer locale.
  
L'impostazione del registro di sistema **SavePassword** dovrebbe essere disattivata quando Skype for business è configurato per supportare l'autenticazione a due fattori. Per impedire agli utenti di salvare le password, modificare la seguente voce del registro di sistema nella workstation locale o utilizzare il modello amministrativo Skype for business da applicare a tutti gli utenti di un determinato pool utilizzando criteri di gruppo:
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>Riproduzione di token AD FS 2,0

AD FS 2,0 fornisce una funzionalità denominata rilevamento della riproduzione di token, in base al quale è possibile rilevare più richieste di token utilizzando lo stesso token e quindi eliminarle. Quando questa funzionalità è abilitata, il rilevamento della riproduzione di token protegge l'integrità delle richieste di autenticazione sia nel WS-Federation profilo passivo che nel profilo WebSSO SAML assicurandosi che lo stesso token non venga mai utilizzato più di una volta.
  
Questa funzionalità deve essere abilitata in situazioni in cui la sicurezza è un problema molto elevato, ad esempio quando si utilizzano i chioschi. Per ulteriori informazioni sul rilevamento della riproduzione di token, vedere [procedure consigliate per la pianificazione e la distribuzione sicure di ad FS 2,0](https://go.microsoft.com/fwlink/p/?LinkId=309215).
  
## <a name="external-user-access"></a>Accesso utente esterno

La configurazione di un proxy ADFS o di un proxy inverso per il supporto dell'autenticazione a due fattori di Skype for business da reti esterne non è illustrata in questi argomenti.
  
## <a name="see-also"></a>Vedere anche

[Configurare l'autenticazione a due fattori in Skype for Business Server](configure-two-factor.md)
  
