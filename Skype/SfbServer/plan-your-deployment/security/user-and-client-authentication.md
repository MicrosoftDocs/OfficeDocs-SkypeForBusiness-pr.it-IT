---
title: Autenticazione utente e client per Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Un utente attendibile è un utente le cui credenziali sono state autenticate da un server attendibile in Skype for Business Server. Tale server è in genere un server Standard Edition, Enterprise Edition Front End o Director. Skype for Business Server si basa su Servizi di dominio Active Directory come unico archivio back-end attendibile delle credenziali utente.
ms.openlocfilehash: d256efdf69afce16a06b3b055a9446b29deb7cb0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737642"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Autenticazione utente e client per Skype for Business Server
 
Un utente attendibile è un utente le cui credenziali sono state autenticate da un server attendibile in Skype for Business Server. Tale server è in genere un server Standard Edition, Enterprise Edition Front End o Director. Skype for Business Server si basa su Servizi di dominio Active Directory come unico archivio back-end attendibile delle credenziali utente.
  
Per autenticazione si intende la fornitura delle credenziali utente a un server trusted. Skype for Business Server i protocolli di autenticazione seguenti, a seconda dello stato e della posizione dell'utente.
  
- **Protocollo di sicurezza MIT Kerberos versione 5** per gli utenti interni con credenziali di Active Directory. Kerberos richiede la connettività client a Servizi di dominio Active Directory, pertanto non può essere utilizzato per l'autenticazione di client esterni al firewall aziendale.
    
- **Protocollo NTLM** per gli utenti con credenziali di Active Directory che si connettono da un endpoint esterno al firewall aziendale. Il servizio Access Edge passa le richieste di accesso a un Director, se presente, o a un Front End Server per l'autenticazione. Il servizio Access Edge in sé non esegue alcuna autenticazione.
    
    > [!NOTE]
    > Il protocollo NTLM offre una minore protezione dagli attacchi rispetto a Kerberos, pertanto viene utilizzato il meno possibile da alcune organizzazioni. Di conseguenza, l'accesso Skype for Business Server può essere limitato a client interni o connessi tramite una connessione VPN o DirectAccess. 
  
- **Protocollo digest** per i cosiddetti utenti anonimi. Gli utenti anonimi sono utenti esterni che non dispongono di credenziali di Active Directory riconosciute, ma che sono stati invitati a una conferenza locale e sono in possesso di una chiave di conferenza valida. L'autenticazione del digest non viene utilizzata per altre interazioni client.
    
Skype for Business Server'autenticazione è costituita da due fasi:
  
1. Viene stabilita un'associazione di sicurezza tra il client e il server.
    
2. Il client e il server utilizzano l'associazione di sicurezza esistente per firmare i messaggi inviati e per verificare i messaggi ricevuti. I messaggi non autenticati provenienti da un client non vengono accettati quando viene abilitata l'autenticazione nel server.
    
L'attendibilità utente è associata a ogni messaggio originato da un utente e non all'identità dell'utente. Il server verifica in ogni messaggio la validità delle credenziali utente. Se le credenziali utente sono valide, il messaggio non riceve richieste di autenticazione non solo dal primo server che lo riceve, ma anche da tutti gli altri server del cloud di server trusted.
  
Gli utenti con credenziali valide emesse da un partner federato sono attendibili, ma è possibile che a causa di vincoli aggiuntivi non sia loro consentito di usufruire di tutti i privilegi accordati agli utenti interni.
  
I protocolli ICE e TURN utilizzano inoltre la richiesta di autenticazione del digest come descritto nella specifica RFC TURN IETF.
  
I certificati client forniscono un modo alternativo per autenticare gli utenti Skype for Business Server. Invece di fornire un nome utente e una password, gli utenti dispongono di un certificato e della chiave privata corrispondente al certificato necessario per risolvere una richiesta di verifica crittografica. Questo certificato deve avere un nome soggetto o un nome alternativo del soggetto che identifichi l'utente e che sia emesso da una CA radice attendibile dai server che eseguono Skype for Business Server, che sia entro il periodo di validità del certificato e che non sia stato revocato. Per essere autenticati, gli utenti devono solo digitare un PIN. I certificati sono particolarmente utili per telefoni, telefoni cellulari e altri dispositivi in cui è difficile immettere un nome utente e una password.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Requisiti di crittografia dovuti a ASP.NET 4.5 

A partire Skype for Business Server 2015 CU5, AES non è supportato per ASP.NET 4.6 e ciò potrebbe causare un errore di avvio dell'app Riunioni Skype. Se un client utilizza AES come valore di convalida della chiave del computer, sarà necessario reimpostare il valore della chiave del computer su SHA-1 o su un altro algoritmo supportato a livello di sito dell'app riunioni di Skype in IIS. Se necessario, vedere [Gestione configurazione ASP.NET IIS 8.0](/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) per istruzioni.
  
Altri valori supportati sono:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  I valori AES, 3DES e MD5 non sono più consentiti, in quanto una volta erano ASP.NET 4. [Miglioramenti della crittografia in ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) include ulteriori dettagli.
