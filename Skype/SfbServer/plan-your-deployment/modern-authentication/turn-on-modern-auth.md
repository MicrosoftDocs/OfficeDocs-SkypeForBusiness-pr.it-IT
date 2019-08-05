---
title: Pianificazione per disattivare i metodi di autenticazione legacy internamente e esternamente alla rete
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: In questo articolo vengono illustrati i cmdlet che consentono agli amministratori un maggiore controllo dei metodi di autenticazione usati all'interno e all'esterno di un'azienda. Gli amministratori possono attivare o disattivare i metodi di autenticazione internamente o esternamente alla rete.
ms.openlocfilehash: aaee46b04832cc114f895f905c180fe089d7349d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194920"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Pianificazione per disattivare i metodi di autenticazione legacy internamente e esternamente alla rete.

> [!NOTE]
> Se si sta per leggere questo articolo, è consigliabile conoscere le topologie di autenticazione moderna supportate, ADAL e la configurazione di autenticazione moderna, ma, in caso contrario, ecco gli articoli che è necessario iniziare: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
L'autenticazione moderna non consente solo i metodi di autenticazione più sicuri, ad esempio auth a due fattori o autenticazione basata su certificati, che può eseguire l'autorizzazione dell'utente senza che sia necessario un nome utente o una password. È piuttosto comodo.

Questo articolo ti aiuterà a inserire i buchi che sono stati sfruttati per attacchi DOS (Denial of Service) su Skype for Business Server, disattivando i metodi meno recenti usati per l'autenticazione, esternamente, internamente o entrambi, alla rete. Ad esempio, un buon metodo per evitare attacchi DOS potrebbe essere disattivare l'autenticazione integrata di Windows (che include NTLM e Kerberos). Se si disattiva l'autenticazione NTLM esternamente e si fa affidamento su un certificato, è utile proteggere le password dall'esposizione. Il motivo è che NTLM usa le credenziali di password per autenticare gli utenti, ma l'autenticazione basata su certificati, abilitata da autenticazione moderna. Questo significa che un'opzione ideale per ridurre gli attacchi DOS consiste nel bloccare l'NTLM esternamente e usare solo l'autenticazione basata su certificati.

Bene, iniziamo.

## <a name="what-would-you-be-changing"></a>Cosa cambierebbe? 

Questi cmdlet funzionano sia per i punti di accesso SIP che per i servizi Web. Anche se questi due canali usano metodi di accesso diversi, eseguendo la gamma da NTLM e Kerberos per l'accesso anonimo, sono stati presi in considerazione tutti i metodi standard usati da Skype for business.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Come ottenere i cmdlet Get e set-CsAuthConfig

Questi cmdlet verranno installati solo dopo l'aggiornamento cumulativo di luglio 2018 (6.0.9319.534) per Microsoft Skype for Business Server 2015 e quindi sono disponibili diverse topologie che possono essere distribuite per il server Skype for business.

## <a name="topologies"></a>Tecnologie

È importante ricordare che queste sono le topologie supportate coinvolte in questo scenario. Per ottenere assistenza per il blocco di un metodo, ad esempio, è necessario disporre di una configurazione tra i tipi seguenti. 

> [!IMPORTANT]
> Nella tabella e nelle descrizioni seguenti l' *autenticazione moderna* è abbreviata come __ma__ e *l'autenticazione integrata di Windows* è abbreviata come __Win__. Come promemoria, l'autenticazione integrata di Windows è costituita da due metodi: NTLM e autenticazione Kerberos. È necessario saperlo per leggere correttamente la tabella.


|       |Esternamente  |Internamente  |Parametro  |
|---------|:---------|:---------|---------|
|__Digitare 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Digitare 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Digitare 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Digitare 4__   |  MA       | Vincere        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Digitare 5__   |  MA + Win       | Vincere        | BlockModernAuthInternally         |

__Descrizione tipo 1:__ Questo è lo scenario predefinito __in__ cui ma è attivato per Skype for Business Server. In altre parole, questo è il *punto di partenza* in cui è configurato ma.

__Descrizione tipo 2:__ Questa topologia blocca ** l'autenticazione NTLM esternamente, ma consente l'utilizzo *interno*di NTLM o Kerberos (per i client che non supportano adal). Se i client supportano ADAL, utilizzeranno MA internamente.

__Digitare 3 Descrizione:__ Questa topologia richiede MA per tutti gli utenti. Tutti i client in grado di ADAL funzioneranno in questa topologia e le password non verranno sfruttate se, ad esempio, si disattiva l'uso di password con l'autenticazione basata su certificati.

__Digitare 4 Descrizione:__ Questa topologia blocca ** l'autenticazione NTLM esternamente e ma internamente. Consente a *tutti i client* di usare internamente ** i metodi di autenticazione legacy (anche client in grado di adal).

__Digitare 5 Descrizione:__ *Esternamente*, i clienti di adal moderni useranno ma e tutti i client che non supportano adal utilizzeranno i metodi di autenticazione legacy. Ma, *internamente* *tutti i client* useranno l'autenticazione legacy (inclusi tutti i client in grado di adal).

È abbastanza facile perdere le tracce dell'obiettivo di proteggere le password nelle opzioni disponibili. Tieni presente che la situazione ideale consiste nell'usare MA esternamente, ad esempio configurando l'autenticazione basata su certificati, per evitare attacchi DOS. Se si sfrutta internamente per i clienti moderni, è anche possibile usare la rete per gli attacchi DOS di Skype for Business Server.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Perché usare set-CsAuthConfig a livello globale

La `Set-CsAuthConfig` configurazione degli effetti cmdlet sia per i ruoli del registrar che per i servizi Web.

Questo cmdlet è concepito per l'esecuzione a livello globale di Skype for Business Server. *Può* essere eseguito a livello di pool, ma non è *consigliabile* perché aggiungerà complessità all'installazione. Eseguendo questi comandi a livello di pool, se il pool non include tutti i ruoli inclusi, ad esempio se non ha servizi Web, le impostazioni verranno impostate solo per il ruolo di registrar. In questo caso, i servizi Web proseguiranno con le impostazioni del livello globale, che possono essere un comportamento confusionario (in particolare quando ciò viene fatto in modo involontario).

Se un client usa le impostazioni del registrar da un pool e le impostazioni dei servizi Web di un altro pool e le impostazioni di autenticazione sono in uno stato incoerente, i client potrebbero non essere in grado di accedere.

Inoltre, se è presente un solo ruolo per un pool: 
* Set-verranno impostate solo le impostazioni che corrispondono al ruolo esistente. Nessun avviso speciale verrà assegnato perché alcune impostazioni *non* sono state impostate. 
* Get-restituirà l'impostazione corrispondente al ruolo esistente e le impostazioni globali per il ruolo che non esiste.
* Se non è presente alcun ruolo per un pool, sia set-che Get-restituiranno un messaggio di errore.
* Se entrambi i ruoli sono presenti per un pool ma i criteri non vengono definiti a livello di pool, Get-restituirà un messaggio di errore.

Potrebbe essere più saggio eseguire un Get-per questi valori e screenshot o registrare lo stato iniziale prima di apportare le modifiche desiderate. È anche possibile tenere in considerazione un log delle modifiche in OneNote.

> [!NOTE]
> 
> Nota: dopo la configurazione di CsAuthConfig, è necessario eseguire Enable-CsComputer in ogni computer in modo che le impostazioni abbiano effetto.

> [!IMPORTANT]
> Se si usa Lync Web Access (LWA) e si deve usare l'accesso basato su moduli (FBA) per l'accesso esterno, riconfigurare LWA in modo che i client possano accedervi con l'accesso anonimo per supportare questi scenari. Allo stesso modo, se si usa il pin di accesso esterno, FBA verrà bloccato solo per gli utenti esterni. Se è necessario modificare il PIN, sarà necessario accedere alla propria società per farlo, internamente.

## <a name="links"></a>Collegamenti 
- Per altre informazioni su PowerShell:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/en-us/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Per altre indicazioni su come usare i comandi o sul CU necessario per installarli:
    - [Briefing cmdlet](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Aggiornamenti per Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015) Generale
    - [2018 di luglio Skype for Business Server 2015, componenti principali cu](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
