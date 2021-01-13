---
title: Gestibilità e strumenti per Skype room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leggere questo argomento per informazioni sugli strumenti di gestione per Skype room System.
ms.openlocfilehash: f46d636bba0779cc42532cc2110ef94abdb6b982
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805796"
---
# <a name="skype-room-system-manageability-and-tools"></a>Gestibilità e strumenti per Skype room System
 
Leggere questo argomento per informazioni sugli strumenti di gestione per Skype room System.
  
## <a name="administrative-portal"></a>Portale amministrativo

Per le distribuzioni locali di Skype for Business Server, è possibile utilizzare il portale di amministrazione di Skype room System per gestire e monitorare attivamente le distribuzioni del sistema room Skype all'interno dell'organizzazione.
  
Per ulteriori informazioni, vedere l'articolo seguente:
  
- [Distribuire il portale Web amministrativo di SRS V1 in Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Elenco di controllo di Exchange

- Verificare che l'individuazione automatica sia configurata e che sia disponibile un RECORD A/CNAME DNS interno per autodiscover.domain.com.
    
- Individuazione automatica ping (ad esempio, ping Autodiscover.contoso.com).
    
- Testare il servizio di individuazione automatica con lo strumento Analizzatore connettività Microsoft. Scegliere il primo test, "non è possibile accedere con Office Outlook".
    
- Se nella sala riunioni è già presente una cassetta postale per le risorse, estendere questo account per il sistema della sala Skype (script di esempio nella parte inferiore della pagina).
    
## <a name="skype-for-business-checklist"></a>Elenco di controllo di Skype for business

- Eseguire gli strumenti seguenti:
    
  - Skype for Business Best Practices Analyzer     
  - Strumento di analisi integrità di Skype for business (Excel)    
  - Analizzatore della connettività di Skype for Business 32 bit o 64 bit
    
- Esaminare [i nuovi strumenti di analisi e risoluzione dei problemi utili per Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/). Conferma di disporre di un pool Skype for business e di un server Office Web Apps e può condividere un deck di PowerPoint utilizzando il client Skype for business.
    
- Se nella sala riunioni è già presente una cassetta postale per le risorse, abilitarla per Skype for business.
    
- Se necessario, richiedere un DID (numero di telefono) per il sistema sala riunioni e aggiornare il campo telefono generale nello strumento Active Directory.
    
## <a name="network"></a>Rete

- Assicurarsi di disporre di una connessione di rete cablata per il sistema di chat in Skype room.
    
- Leggere la guida alla pianificazione della rete per Skype for business.
    
- Richiedere una valutazione della rete Skype for business da un partner di Skype for business.
    
- Leggere i dati sulle prestazioni acquisiti nello strumento di analisi dell'integrità di Skype for business (Excel).
    
- Eseguire lo strumento di analisi della rete.
    
- Eseguire lo strumento di diagnostica prima chiamata.
    
## <a name="skype-room-system-security"></a>Sicurezza del sistema delle chat room Skype

Skype room System è un sistema incorporato che può essere completamente integrato in una distribuzione di Windows, usando il modello di sicurezza di Skype for business, la gestione dei diritti e gli strumenti di gestione, ad esempio SCOM. Le caratteristiche includono:
  
- Filtro di scrittura per impedire la scrittura su disco in modalità utente 
    
- App Locker per impedire l'esecuzione di app non autorizzate. Tutte le porte USB sono disattivate in modalità utente.
    
  - Nessuna app standard o visualizzatori risiedono nell'hardware del sistema Skype room. Viene eseguito il rendering di tutti i contenuti tramite protocolli HTTP o RDP.
    
  - Il PC del dispositivo esegue il sistema operativo Windows Embedded Standard 7. Tutto l'hardware, inclusi i dispositivi, è fornito dai partner OEM.
    
  - Join di dominio facoltativo a servizi di dominio Active Directory, abilitazione del controllo e gestione degli account di sicurezza locali.
    
- È inoltre possibile gestire l'account amministratore locale utilizzando l'interfaccia di amministrazione di Skype for business.
    
- Skype room System viene aggiornato tramite i processi di aggiornamento standard di Microsoft.
    
- Skype for business è connesso al sistema di chat room.
    
  - Skype for business utilizza la crittografia end-to-end e l'autorizzazione per tutte le modalità di comunicazione
    
  - Skype room System supporta gli standard di sicurezza e conformità di Skype for business. Per ulteriori informazioni, vedere [pianificare la sicurezza in Skype for Business Server](../../plan-your-deployment/security/security.md) .
    
## <a name="license"></a>License

Verificare di utilizzare un servizio di gestione delle chiavi per l'attivazione del software. In caso affermativo, potrebbe essere necessario controllare o aggiungere la chiave del servizio di gestione delle chiavi del client Skype for business. Se non si utilizza il servizio di gestione delle chiavi, richiedere la chiave per contratti multilicenza per il MAK client Skype for business.
  
## <a name="license-keys"></a>Codici di licenza

Skype room System esegue il client desktop Skype for business in background. Se Skype room System è un membro del dominio, verrà individuato il servizio di gestione delle chiavi. Se si dispone del tasto di gestione delle licenze per contratti multilicenza, verrà attivato automaticamente. Contratti multilicenza fornisce anche un codice MAK, che viene immesso come visualizzato come xxxxx-xxxxx-xxxxx-xxxxx. (È necessario l'accesso a Internet per l'attivazione tramite MAK ma non il servizio di gestione delle chiavi). Per ulteriori informazioni, vedere Volume Activation of Office 2013.
  
- Per immettere il codice "MAK key", andare a impostazioni OEM \> SRS Licensing Tool. Fare clic su Controlla stato. Quando lo stato indica che "il prodotto non è attivato", immettere il tasto.
    
- Se durante l'attivazione viene visualizzato un messaggio di errore che indica che "' il servizio di gestione delle licenze software ha riferito che il codice Product Key non è valido", verificare che:
    
  - Il tasto è stato immesso correttamente.
    
  - È stato immesso il codice MAK di Skype for business e non un altro tasto.
    
  - Il sistema dispone di accesso a Internet.
    
- È possibile attivarlo tramite telefono, ma è necessario tentare di attivarlo prima usando lo strumento di gestione delle licenze SRS. Per attivare tramite telefono, avviare una riunione di prova (non una chiamata di prova che è troppo breve). Nella procedura guidata di attivazione di Office, selezionare Attivazione telefono, chiamare Microsoft, digitare il numero lungo e immettere una risposta.
    
## <a name="certificate-authority"></a>Autorità di certificazione

Confermare che l'autorità di certificazione utilizzata per rilasciare il certificato di Office Web Apps Server 2013 disponga di un percorso HTTP incluso nella proprietà dell'elenco di revoche di certificati.
  
Importare il file di certificato (con estensione CRT) in Skype room System se si utilizza Skype for Business Server. È facilmente reperibile dalla condivisione CertEnroll del server CA o nella cartella radice attendibile di qualsiasi dominio aggiunto al PC.
  
## <a name="certificates"></a>Certificati

Verificare che l'autorità di certificazione disponga di un percorso http per l'elenco di revoche di certificati. In caso contrario, aggiornare l'autorità di certificazione per includerne una.
  
Installare i certificati nel programma di installazione di amministrazione del sistema della sala Skype in Gestione certificati delle impostazioni di sistema \> . È necessaria la CA radice dell'organizzazione per il certificato interno.
  
Un modo per ottenere i certificati necessari consiste nell'individuare l'autorità di certificazione che ha emesso i certificati. Per Skype for Business Server, su un PC in Skype for business, fare clic su impostazioni \> \> conferenza telefonica con accesso esterno. Verrà aperta una pagina Web protetta dall'autorità di certificazione che ha emesso i certificati interni. Fare clic sull'icona Blocca sulla barra degli indirizzi del browser per visualizzare un rapporto sulla sicurezza. Fare clic su Visualizza certificati ed esaminare la proprietà del punto di distribuzione CRL. Il secondo parametro CN deve corrispondere al nome del server dell'autorità di certificazione. Ora aprire Esplora risorse per l'indirizzo \\ \< CA Server Name \> \CertEnroll. Copiare i due file con estensione CRL e il file. CRT in un'unità flash e posizionarlo sul lato sinistro della scheda SMART.
  
Importare il file. CRT in Skype room System sotto la cartella Trusted room Certification Authority.
  
Importare i file con estensione CRL su Skype room System sotto la cartella autorità di certificazione intermedie. (È necessario modificare il filtro dell'estensione di file in Gestione certificati in. CRL per visualizzare i file).
  
Nota: il server Office Web Apps 2013 può condividere la stessa CA di Skype for business. In caso contrario, non sarà possibile condividere PowerPoint in una riunione. Controllare con esso e ottenere i file CRT e CRL dalla rete di condivisione CertEnroll come spiegato in precedenza. 
  
L'appartenenza al dominio è in grado di semplificare alcuni aspetti perché è possibile gestire il sistema delle sale Skype come sistema di Windows e può essere affidato ad Active Directory per alcuni dei relativi elementi. Tuttavia, è preferibile gestirla manualmente.
  

