---
title: Gestibilità e strumenti del sistema skype room
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
description: Leggere questo argomento per informazioni sugli strumenti di gestione per Skype Room System.
ms.openlocfilehash: 81adbb93c71abc201d9099d86e8414a524d85dff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093550"
---
# <a name="skype-room-system-manageability-and-tools"></a>Gestibilità e strumenti del sistema skype room
 
Leggere questo argomento per informazioni sugli strumenti di gestione per Skype Room System.
  
## <a name="administrative-portal"></a>Portale amministrativo

Per le distribuzioni locali di Skype for Business Server, è possibile utilizzare il portale amministrativo di Skype Room System per gestire e monitorare attivamente le distribuzioni di Skype Room System all'interno dell'organizzazione.
  
Per ulteriori informazioni, vedere l'articolo seguente:
  
- [Distribuire il portale Web amministrativo di SRS v1 in Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Elenco di controllo di Exchange

- Verificare che l'individuazione automatica sia impostata e che sia disponibile un record A/CNAME DNS interno per autodiscover.domain.com.
    
- Ping autodiscover (ad esempio, Ping Autodiscover.contoso.com).
    
- Testare il servizio di individuazione automatica con Microsoft Connectivity Analyzer Tool. Scegliere il primo test, "Non è possibile accedere con Office Outlook".
    
- Se la sala riunioni dispone già di una cassetta postale per le risorse, estendere questo account per skype room system (script di esempio nella parte inferiore della pagina).
    
## <a name="skype-for-business-checklist"></a>Elenco di controllo di Skype for Business

- Eseguire gli strumenti seguenti:
    
  - Skype for Business Best Practices Analyzer     
  - Strumento di analisi dell'integrità di Skype for Business (Excel)    
  - Analizzatore del servizio di integrazione applicativa di Skype for Business a 32 bit o a 64 bit
    
- Rivedere Utili nuovi strumenti di risoluzione dei problemi [e analisi per Office 365.](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365) Verificare di disporre di un pool Skype for Business e di un server Office Web Apps e di poter condividere una presentazione di PowerPoint utilizzando il client Skype for Business.
    
- Se la sala riunioni dispone già di una cassetta postale per le risorse, abilitarla per Skype for Business.
    
- Se necessario, richiedere un DID (numero di telefono) per il sistema sala riunioni e aggiornare il campo Telefono generale nello strumento Active Directory.
    
## <a name="network"></a>Rete

- Assicurati di avere una connessione di rete cablata per skype room system.
    
- Leggere la Guida alla pianificazione della rete per Skype for Business.
    
- Richiedere una valutazione di rete Skype for Business da un partner Skype for Business.
    
- Leggere i dati sulle prestazioni acquisiti nello strumento di analisi dell'integrità di Skype for Business (Excel).
    
- Eseguire lo strumento di analisi di rete.
    
- Eseguire lo strumento di diagnostica pre-chiamata.
    
## <a name="skype-room-system-security"></a>Skype Room System Security

Skype Room System è un sistema incorporato che può essere completamente integrato in una distribuzione di Windows, utilizzando il modello di sicurezza, la gestione dei diritti e gli strumenti di gestione di Skype for Business, ad esempio SCOM. Le funzionalità includono:
  
- Un filtro di scrittura per impedire la scrittura su disco in modalità utente 
    
- App Locker per impedire l'esecuzione di app non autorizzate. Tutte le porte USB sono disabilitate in modalità utente.
    
  - Nessuna app o visualizzatore standard si trova nell'hardware di Skype Room System. Il rendering di tutto il contenuto viene eseguito tramite protocolli HTTP o RDP.
    
  - Il PC dell'appliance esegue il sistema operativo Windows Embedded Standard 7. Tutti i componenti hardware, inclusi i dispositivi, sono forniti dai partner OEM.
    
  - Aggiunta facoltativa al dominio a Servizi di dominio Active Directory, abilitando la gestione e il controllo degli account di sicurezza locali.
    
- Puoi anche gestire l'account amministratore locale usando l'interfaccia di amministrazione di Skype for Business.
    
- Skype Room System viene aggiornato tramite i processi standard di Microsoft Update.
    
- Skype Room System si connette con Skype for Business.
    
  - Skype for Business usa la crittografia end-to-end e l'autorizzazione per tutte le modalità di comunicazione
    
  - Skype Room System supporta gli standard di sicurezza e conformità di Skype for Business. Per [altre informazioni, vedi Pianificare la sicurezza in Skype For Business Server.](../../plan-your-deployment/security/security.md)
    
## <a name="license"></a>License

Verificare di utilizzare un servizio di gestione delle chiavi per l'attivazione del software. In tal caso, potrebbe essere necessario controllare o aggiungere il codice KMS del client Skype for Business. Se non si utilizza il servizio di gestione delle chiavi, richiedere il codice "Product Key" per contratti multilicenza per il codice "Product Key" del client Skype for Business.If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.
  
## <a name="license-keys"></a>Codici di licenza

Skype Room System esegue il client desktop Skype for Business in background. Se Skype Room System è un membro del dominio, scoprirà il servizio di gestione delle chiavi. (e se ha il codice KMS per contratti multilicenza, verrà attivato automaticamente). I contratti multilicenza forniscono anche un codice ADK, che viene immesso quando viene visualizzato xxxxx-xxxxx-xxxxx-xxxxx. È necessario l'accesso a Internet per l'attivazione tramite codice "Product Key" ma non con il servizio di gestione delle chiavi. Per ulteriori informazioni, vedere Volume activation of Office 2013.
  
- Per immettere il codice ADK, passare a OEM Settings \> SRS Licensing Tool. Fare clic su Controlla stato. Quando lo stato indica "il prodotto non è attivato", immetti il codice.
    
- Se durante l'attivazione viene visualizzato un errore che indica "Il servizio gestione licenze software ha segnalato che il codice Product Key non è valido", verificare che:
    
  - Il tasto è stato immesso correttamente.
    
  - È stato immesso il codice ADK di Skype for Business e non un altro tasto.
    
  - Il sistema ha accesso a Internet.
    
- È possibile eseguire l'attivazione tramite telefono, ma è necessario aver tentato di eseguire l'attivazione utilizzando lo strumento di gestione delle licenze SRS. Per eseguire l'attivazione tramite telefono, avviare una riunione di prova (non una chiamata di prova perché è troppo breve). Nell'Attivazione guidata di Office selezionare Attivazione telefonica, chiamare Microsoft, digitare il numero lungo e immettere una risposta.
    
## <a name="certificate-authority"></a>Autorità di certificazione

Verificare che l'autorità di certificazione utilizzata per emettere il certificato di Office Web Apps Server 2013 abbia un percorso HTTP incluso nella proprietà Certificate Revocation List.
  
Importare il file del certificato (con estensione crt) nel sistema skype room se si usa Skype for Business Server. È facilmente ottenuta dalla condivisione CertEnroll del server CA o nella cartella Radice attendibile di qualsiasi DOMINIO aggiunto al PC.
  
## <a name="certificates"></a>Certificati

Verificare che l'Autorità di certificazione abbia un percorso http per l'elenco di revoche di certificati. In caso contrario, aggiornare l'autorità di certificazione per includerne una.
  
Installare i certificati nella configurazione dell'amministratore di Skype Room System in System Settings \> Certificate Manager. È necessaria l'autorità di certificazione radice dell'organizzazione per il certificato interno.
  
Un modo per ottenere i certificati necessari è individuare l'autorità di certificazione che ha emesso i certificati. Per Skype for Business Server, in un PC in Skype for Business, fare clic su Impostazioni \> Strumenti Impostazioni conferenza telefonica con accesso \> remoto. Verrà aperta una pagina Web protetta dall'autorità di certificazione che ha emesso i certificati interni. Fare clic sull'icona Blocca sulla barra degli indirizzi del browser per visualizzare un report sulla sicurezza. Fare clic su Visualizza certificati ed esaminare la proprietà Punto di distribuzione CRL. Il secondo parametro CN deve essere il nome del server dell'autorità di certificazione. Ora apri Esplora risorse per \\ \< CA Server Name \> l'indirizzo \CertEnroll. Copiare i due file crl e il file crt in un'unità flash e metterlo nella parte sinistra della scheda SMART.
  
Importare il file crt nel sistema skype room nella cartella Autorità di certificazione sala attendibile.
  
Importare i file CRL nel sistema skype room nella cartella Autorità di certificazione intermedie. È necessario modificare il filtro delle estensioni di file in Gestione certificati in .crl per visualizzare i file.
  
Nota: il server Office Web Apps 2013 può condividere la stessa CA di Skype for Business. In caso di problema, non sarà possibile condividere PowerPoint in una riunione. Verificare con l'IT e ottenere i file CRT e CRL dalla condivisione di rete CA CertEnroll, come spiegato in precedenza. 
  
L'appartenenza al dominio può semplificare alcuni aspetti perché è possibile considerare skype room system come un sistema Windows e può fare affidamento su Active Directory per alcuni degli aspetti del certificato. Tuttavia, è meglio gestirlo manualmente.
