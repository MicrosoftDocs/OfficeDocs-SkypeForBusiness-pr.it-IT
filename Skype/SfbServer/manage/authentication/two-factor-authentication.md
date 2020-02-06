---
title: Gestire l'autenticazione a due fattori in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 90dc286e247c0c6eeb75bb884071b85e57663278
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818718"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Gestire l'autenticazione a due fattori in Skype for Business Server
 
**Riepilogo:** Gestire l'autenticazione a due fattori in Skype for Business Server.
  
L'autenticazione a due fattori consente di migliorare la sicurezza richiedendo agli utenti di fornire due forme di autenticazione o di identificazione, ovvero una combinazione nome utente/password e un token o un certificato. Questo è anche noto come "qualcosa che hai, qualcosa che conosci". 
  
Un esempio tipico di autenticazione a due fattori con un certificato è l'uso di smart card. Una smart card contiene un certificato associato all'account utente e può essere convalidato in base alle informazioni sull'utente e sul certificato archiviate in un server. Confrontando le informazioni utente (nome utente e password) con il certificato fornito, il server convalida le credenziali e autentica l'utente.
  
Quando configuri un ambiente di Skype for Business Server per supportare l'autenticazione a due fattori, considera gli argomenti seguenti.
  
## <a name="client-support"></a>Supporto client

Gli aggiornamenti cumulativi per Lync Server 2013: client desktop di luglio 2013 e il client Skype for business sono gli unici client che attualmente supportano l'autenticazione a due fattori.
  
## <a name="topology-requirements"></a>Requisiti di topologia

I clienti sono fortemente incoraggiati a distribuire l'autenticazione a due fattori usando Skype for Business Server dedicato con i pool di Edge, Director e User. Per abilitare l'autenticazione passiva per gli utenti, è necessario che altri metodi di autenticazione vengano disabilitati per altri ruoli e servizi, inclusi i seguenti:
  
|**Tipo di configurazione**|**Tipo di servizio**|**Ruolo del server**|**Tipo di autenticazione da disabilitare**|
|:-----|:-----|:-----|:-----|
|Servizio Web  <br/> |WebServer  <br/> |Director  <br/> |Kerberos, NTLM e certificato  <br/> |
|Servizio Web  <br/> |WebServer  <br/> |Front-end  <br/> |Kerberos, NTLM e certificato  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Bordo  <br/> |Kerberos e NTLM  <br/> |
|Proxy  <br/> |Registrar  <br/> |Front-end  <br/> |Kerberos e NTLM  <br/> |
   
A meno che questi tipi di autenticazione non siano disabilitati a livello di servizio, tutte le altre versioni del client non saranno in grado di accedere correttamente quando l'autenticazione a due fattori è abilitata all'interno della distribuzione.
  
## <a name="skype-for-business-service-discovery"></a>Individuazione del servizio Skype for business

I record DNS usati dai client interni e/o esterni per individuare i servizi Skype for business devono essere configurati per la risoluzione in un server Skype for business non abilitato per l'autenticazione a due fattori. Con questa configurazione, gli utenti di pool Skype for business che non sono abilitati per l'autenticazione a due fattori non saranno obbligatori ad immettere un PIN da autenticare, mentre gli utenti di pool Skype for business abilitati per l'autenticazione a due fattori saranno obbligatorio per immettere il PIN per l'autenticazione.
  
## <a name="exchange-authentication"></a>Autenticazione di Exchange

I clienti che hanno distribuito l'autenticazione a due fattori per Microsoft Exchange potrebbero non essere disponibili per alcune funzionalità del client. Questa funzionalità è attualmente in fase di progettazione, perché il client Skype for business non supporta l'autenticazione a due fattori per le caratteristiche che dipendono dall'integrazione di Exchange.
  
## <a name="contacts"></a>Contatti

Gli utenti di Skype for business configurati per sfruttare la caratteristica archivio contatti unificato troveranno che i loro contatti non sono più disponibili dopo l'accesso con l'autenticazione a due fattori.
  
Devi usare il cmdlet **Invoke-CsUcsRollback** per rimuovere i contatti utente esistenti dall'archivio contatti unificato e archiviarli in Skype for Business Server prima di abilitare l'autenticazione a due fattori.
  
## <a name="skill-search"></a>Ricerca di abilità

I clienti che hanno configurato la funzionalità Ricerca competenze nell'ambiente Skype for business troveranno che questa funzionalità non funziona quando Skype for business è abilitato per l'autenticazione a due fattori. In base alla progettazione, poiché in Microsoft SharePoint non è attualmente supportata l'autenticazione a due fattori.
  
## <a name="credentials"></a>Credenziali

Sono disponibili diverse considerazioni sulla distribuzione che includono credenziali salvate di Skype for business che potrebbero influire sugli utenti configurati per l'uso dell'autenticazione a due fattori.
  
### <a name="deleting-saved-credentials"></a>Eliminazione delle credenziali salvate

Gli utenti devono usare l'opzione **Elimina le informazioni di accesso** nel client Skype for business ed eliminare la cartella del profilo SIP da%LocalAppData%\Microsoft\Office\15.0\Skype for business prima di provare a firmare per la prima volta con l'autenticazione a due fattori.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Con il metodo di autenticazione Kerberos o NTLM, le credenziali di Windows dell'utente vengono usate automaticamente per l'autenticazione. In una distribuzione tipica di Skype for Business Server in cui è abilitato Kerberos e/o NTLM per l'autenticazione, gli utenti non devono immettere le proprie credenziali ogni volta che eseguono l'accesso.
  
Se agli utenti vengono richieste involontariamente le credenziali prima che venga chiesto di immettere il PIN, la chiave del registro di sistema **DisableNTCredentials** potrebbe essere configurata involontariamente nei computer client, possibilmente tramite criteri di gruppo.
  
Per evitare che vengano richieste altre credenziali, creare la voce del registro di sistema seguente nella workstation locale o usare il modello amministrativo Skype for business per applicare a tutti gli utenti un pool specifico con criteri di gruppo:
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Quando un utente accede a Skype for business per la prima volta, viene chiesto di salvare la propria password per l'utente. Se selezionata, questa opzione consente di archiviare il certificato client dell'utente nell'archivio dei certificati personali e le credenziali di Windows dell'utente da archiviare in Gestione credenziali del computer locale.
  
L'impostazione del registro di sistema **SavePassword** deve essere disabilitata quando Skype for business è configurato per supportare l'autenticazione a due fattori. Per impedire agli utenti di salvare le proprie password, modificare la voce del registro di sistema seguente nella workstation locale o usare il modello amministrativo Skype for business per applicare a tutti gli utenti un pool specifico con criteri di gruppo:
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>Riproduzione di token AD FS 2,0

ADFS 2,0 offre una caratteristica denominata rilevamento riproduzione token, in base alla quale più richieste di token che usano lo stesso token possono essere rilevate e quindi scartate. Quando questa funzionalità è abilitata, il rilevamento della riproduzione del token protegge l'integrità delle richieste di autenticazione sia nel profilo passivo WS-Federation che nel profilo WebSSO SAML assicurando che lo stesso token non venga mai usato più di una volta.
  
Questa caratteristica deve essere abilitata in situazioni in cui la sicurezza è un problema molto elevato, ad esempio quando si usano i chioschi. Per altre informazioni sul rilevamento della riproduzione di token, vedere [procedure consigliate per la pianificazione e la distribuzione sicure di adfs 2,0](https://go.microsoft.com/fwlink/p/?LinkId=309215).
  
## <a name="external-user-access"></a>Accesso utenti esterni

La configurazione di un proxy ADFS o di un proxy inverso per supportare l'autenticazione a due fattori di Skype for business da reti esterne non è contemplata in questi argomenti.
  
## <a name="see-also"></a>Vedere anche

[Configurare l'autenticazione a due fattori in Skype for Business Server](configure-two-factor.md)
  
