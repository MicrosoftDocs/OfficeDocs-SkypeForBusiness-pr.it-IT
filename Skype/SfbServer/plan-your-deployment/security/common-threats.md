---
title: Minacce alla sicurezza comuni nell'informatica moderna
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/22/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
description: Poiché Skype for Business Server è un sistema di comunicazioni di livello aziendale, è necessario essere consapevoli degli attacchi di sicurezza comuni che potrebbero influire sull'infrastruttura e sulle comunicazioni.
ms.openlocfilehash: d2eff9346c1c2d00af9fb0789f652dfe072702f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832226"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Minacce alla sicurezza comuni nell'informatica moderna
 
Poiché Skype for Business Server è un sistema di comunicazioni di livello aziendale, è necessario essere consapevoli degli attacchi di sicurezza comuni che potrebbero influire sull'infrastruttura e sulle comunicazioni.
  
## <a name="compromised-key-attack"></a>Attacco tramite chiave compromessa

Una chiave è un codice o un numero segreto utilizzato per crittografare, decrittografare o convalidare informazioni segrete. Nell'infrastruttura a chiave pubblica (PKI) sono in uso due chiavi sensibili che devono essere considerate: 
  
- La chiave privata di ogni titolare del certificato
    
- Chiave di sessione utilizzata dopo un'identificazione corretta e uno scambio di chiavi di sessione da parte dei partner che comunicano
    
Un attacco di compromissione della chiave si verifica quando l'autore dell'attacco riesce a determinare la chiave privata o la chiave di sessione. In questo caso, l'autore dell'attacco può utilizzare la chiave per decrittografare i dati crittografati all'insaputa del mittente.
  
Skype for Business Server usa le funzionalità PKI nel sistema operativo Windows Server per proteggere i dati chiave utilizzati per la crittografia per le connessioni TLS (Transport Layer Security). Le chiavi utilizzate per la crittografia multimediale vengono scambiate tramite connessioni TLS.
  
## <a name="network-denial-of-service-attack"></a>Attacco Denial of Service alla rete

L'attacco di tipo Denial of Service si verifica quando l'autore dell'attacco impedisce per gli utenti validi l'utilizzo e il funzionamento normali della rete. Questa operazione viene eseguita quando l'utente malintenzionato inonda il servizio di richieste legittime che sovraccarica l'uso del servizio da parte di utenti legittimi. Utilizzando un attacco Denial of Service, l'utente malintenzionato può eseguire le operazioni seguenti:
  
- Inviare dati non validi alle applicazioni e ai servizi in esecuzione nella rete sottoposta all'attacco per disturbarne il normale funzionamento.
    
- Inviare una grande quantità di traffico, sovraccaricando il sistema finché non smette di rispondere o risponde lentamente a richieste legittime.
    
- Nascondere la prova degli attacchi.
    
- Impedire agli utenti di accedere alle risorse della rete.
    
## <a name="eavesdropping-sniffing-snooping"></a>Eavesdropping (Sniffing, Snooping)

Un attacco eavesdropping può verificarsi quando l'autore di un attacco ottiene l'accesso al percorso dei dati in una rete e ha la possibilità di monitorare e leggere il traffico. Questo tipo di attacco è anche denominato sniffing o snooping. Se il traffico è in testo normale, l'autore dell'attacco può leggerlo quando ottiene l'accesso al percorso. Un esempio è un attacco eseguito controllando un router nel percorso dei dati. 
  
L'impostazione e il suggerimento predefinito per il traffico all'interno di Skype for Business Server sono l'utilizzo di MTLS (Mutual TLS) tra server attendibili e TLS da client a server. Questa misura di protezione renderebbe un attacco molto difficile o impossibile da raggiungere entro il periodo di tempo in cui si verifica una determinata conversazione. TLS autentica tutte le parti e crittografa tutto il traffico. Questo processo non impedisce che si verifichi un attacco eavesdropping, ma l'autore dell'attacco non può leggere il traffico a meno che non venga violata la crittografia.
  
Il protocollo TURN (Traversal Using Relay NAT) non impone la crittografia del traffico e le informazioni che invia sono protette dall'integrità dei messaggi. Anche se è aperto alle intercettazioni, le informazioni che invia (ovvero gli indirizzi IP e la porta) possono essere estratte direttamente esaminando semplicemente gli indirizzi di origine e di destinazione dei pacchetti. Il servizio A/V Edge garantisce che i dati siano validi controllando l'integrità del messaggio utilizzando la chiave derivata da alcuni elementi, inclusa una password TURN, che non viene mai inviata in testo non crittografato. Se si usa SRTP (Secure Real Time Protocol), viene crittografato anche il traffico multimediale.
  
## <a name="identity-spoofing-ip-address-and-caller-id-spoofing"></a>Spoofing dell'identità (spoofing di id chiamante e indirizzo IP)

Lo spoofing delle identità si verifica quando l'utente malintenzionato determina e utilizza un numero di telefono di un utente valido (ID chiamante) o un indirizzo IP di una rete, un computer o un componente di rete senza essere autorizzato a farlo. Un attacco riuscito consente all'autore dell'attacco di operare come se l'autore dell'attacco fosse l'entità normalmente identificata dal numero di telefono (ID chiamante) o dall'indirizzo IP.

Nel contesto di Skype for Business Server, lo spoofing degli indirizzi IP entra in gioco solo se un amministratore ha eseguito entrambe le operazioni seguenti:
  
- Ha configurato connessioni che supportano solo TCP (Transmission Control Protocol). Questa operazione è sconsigliata perché le comunicazioni TCP non vengono crittografate.
    
- Ha contrassegnato gli indirizzi IP di tali connessioni come host attendibile.
    
Il problema non si presenta con le connessioni TLS (Transport Layer Security), in quanto TLS autentica tutte le parti e crittografa tutto il traffico. L'utilizzo di TLS impedisce all'autore di un attacco di eseguire lo spoofing degli indirizzi PI in una connessione specifica, ad esempio MTLS (Mutual TLS). Ma un utente malintenzionato potrebbe comunque effettuare lo spoofing dell'indirizzo del server DNS utilizzato da Skype for Business Server. Tuttavia, poiché l'autenticazione in Skype for Business viene eseguita con certificati, un utente malintenzionato non avrebbe un certificato valido necessario per effettuare lo spoofing di una delle parti nella comunicazione.

D'altra parte, lo spoofing dell'ID chiamante entra in gioco quando è stato stabilito un trunk SIP tra un provider, un gateway PSTN o un altro sistema PBX e Skype for Business Server. In questi casi, Skype for Business Server non offre alcuna protezione per impedire lo spoofing dell'ID chiamante. Ciò significa che un utente di Skype for Business può ricevere una chiamata dal trunk SIP con un ID chiamante falsificato che visualizza il numero di telefono o il nome visualizzato (se si applica la ricerca inversa del numero) di un altro utente Skype for Business. La protezione a questo scopo deve essere applicata sul lato provider, sul gateway PSTN o PBX.
  
## <a name="man-in-the-middle-attack"></a>Attacco man-in-the-middle

Un attacco man-in-the-middle si verifica quando un utente malintenzionato reinstrada la comunicazione tra due utenti attraverso il computer dell'autore dell'attacco all'insaputa dei due utenti che comunicano. L'autore dell'attacco può monitorare e leggere il traffico prima di inviarlo al destinatario previsto. Ogni utente della comunicazione invia e riceve il traffico dall'autore dell'attacco a propria insaputa, pensando di comunicare solo con l'utente previsto. Questa situazione può verificarsi se l'autore di un attacco può modificare Servizi di dominio Active Directory per aggiungere il server come server trusted o modificare DNS (Domain Name System) per fare in modo che i client si connettano all'autore dell'attacco mentre cercano di raggiungere il server. Un attacco man-in-the-middle può verificarsi anche con il traffico multimediale tra due client. Tuttavia, in Skype for Business Server la condivisione di audio, video e applicazioni point-to-point, i flussi vengono crittografati con SRTP, utilizzando chiavi crittografiche negoziate tra i peer che utilizzano SIP (Session Initiation Protocol) su TLS. I server come Group Chat utilizzano HTTPS per aumentare la sicurezza del traffico Web.
  
## <a name="rtp-replay-attack"></a>Attacco di tipo replay RTP

Un attacco di tipo replay si verifica quando una trasmissione multimediale valida tra due parti viene intercettata e ritrasmessa per finalità dannose. SRTP utilizzato insieme a un protocollo di segnalazione sicuro protegge le trasmissioni da attacchi di tipo replay consentendo al destinatario di mantenere un indice dei pacchetti RTP già ricevuti e di confrontare ogni nuovo pacchetto con quelli già elencati nell'indice.
  
## <a name="spim"></a>Spim

I messaggi istantanei indesiderati sono costituiti da messaggi commerciali non richiesti o da richieste di sottoscrizione di presenza. Sebbene non costituiscano in se stessi una violazione della rete, sono quanto meno fastidiosi, possono ridurre la produttività e la disponibilità delle risorse e provocare una violazione della rete. Un esempio di questo tipo è l'invio di richieste indesiderate da un utente a un altro. Ogni utente può bloccare gli altri per evitare questo problema, ma con la federazione, se viene stabilito un attacco coordinato con invio di messaggi istantanei indesiderati, può risultare difficile respingerlo a meno che non si disabiliti la federazione per il partner.
  
## <a name="viruses-and-worms"></a>Virus e worm

Un virus è un'unità di codice il cui scopo è quello di riprodurre altre unità di codice analoghe. Per funzionare, un virus necessita di un host, ad esempio un file, un messaggio di posta elettronica o un programma. Aworm è un'unità di codice il cui scopo è riprodurre unità di codice aggiuntive simili, ma non richiede un host. Virus e worm si presentano principalmente durante il trasferimento di file tra client o quando vengono inviati URL da altri utenti. Se nel computer in uso è presente un virus, questo può ad esempio utilizzare l'identità dell'utente e inviare messaggi istantanei per suo conto.
  
## <a name="personally-identifiable-information"></a>Informazioni personali

Skype for Business Server può divulgare informazioni su una rete pubblica che potrebbero essere collegate a un individuo. È possibile suddividere i tipi di informazioni in due categorie specifiche:
  
- **Dati sulla presenza avanzata** I dati sulla presenza avanzata sono informazioni che un utente può scegliere di condividere o non condividere tramite un collegamento a un partner federato o con i contatti all'interno di un'organizzazione. Questi dati non vengono condivisi con gli utenti di una rete di messaggistica istantanea pubblica. Con i criteri client e altre configurazioni dei client, parte del controllo può venire affidato all'amministratore di sistema. In Skype for Business Server, la modalità privacy della presenza avanzata può essere configurata per un singolo utente per impedire agli utenti di Skype for Business non presenti nell'elenco contatti dell'utente di visualizzare le informazioni sulla presenza dell'utente. La modalità privacy della presenza avanzata non impedisce agli utenti di Microsoft Office Communicator 2007 e Microsoft Office Communicator 2007 R2 di visualizzare le informazioni sulla presenza di un utente. Per informazioni dettagliate sulla distribuzione del client e della [presenza,](../../plan-your-deployment/instant-messaging-and-presence.md)vedere Distribuire client per Skype for Business [Server](../../deploy/deploy-clients/deploy-clients.md) e Pianificare la messaggistica istantanea e la presenza in Skype for Business Server.
    
- **Dati obbligatori** I dati obbligatori sono necessari per il corretto funzionamento del server o del client e NON sono sotto il controllo dell'amministrazione del client o del sistema. Si tratta di informazioni necessarie a livello di server o di rete ai fini del routing, del mantenimento dello stato e della segnalazione.
    
Nelle tabelle seguenti sono elencati i dati esposti su una rete pubblica.
  
**Dati sulla presenza avanzata**

|**Dati divulgati**|**Impostazioni possibili**|
|:-----|:-----|
|Dati personali  <br/> |Nome, Titolo, Società, Indirizzo e-mail, Fuso orario  <br/> |
|Numeri di telefono  <br/> |Ufficio, cellulare, abitazione  <br/> |
|Informazioni del calendario  <br/> |Disponibilità, Avviso fuori città, Dettagli riunione (per gli utenti che hanno accesso al calendario)  <br/> |
|Stato presenza  <br/> |Non al computer, Disponibile, Occupato, Non disturbare, Non in linea  <br/> |
   
**Dati obbligatori**


| **Dati divulgati** | **Informazioni di esempio**                            |
|:-------------------|:---------------------------------------------------|
| Indirizzo IP  <br/>  | Indirizzo effettivo del computer o indirizzo NAT  <br/> |
| URI SIP  <br/>     | jeremylos@litwareinc.com  <br/>                    |

