---
title: Autenticazione utente e client per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Un utente attendibile è quello le cui credenziali sono state autenticate da un server attendibile in Skype for Business Server. Tale server è in genere un server Standard Edition, Enterprise Edition Front End o Director. Skype for Business Server si basa su servizi di dominio Active Directory come singolo archivio back-end attendibile delle credenziali utente.
ms.openlocfilehash: bf0bde8478cd6c4e2eb068ffade7fba7fac14d56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832006"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Autenticazione utente e client per Skype for Business Server
 
Un utente attendibile è quello le cui credenziali sono state autenticate da un server attendibile in Skype for Business Server. Tale server è in genere un server Standard Edition, Enterprise Edition Front End o Director. Skype for Business Server si basa su servizi di dominio Active Directory come singolo archivio back-end attendibile delle credenziali utente.
  
Per autenticazione si intende la fornitura delle credenziali utente a un server trusted. Skype for Business Server utilizza i seguenti protocolli di autenticazione, a seconda dello stato e della posizione dell'utente.
  
- **Protocollo di sicurezza MIT Kerberos versione 5** per gli utenti interni con credenziali di Active Directory. Kerberos richiede la connettività client a Servizi di dominio Active Directory, pertanto non può essere utilizzato per l'autenticazione di client esterni al firewall aziendale.
    
- **Protocollo NTLM** per gli utenti con credenziali di Active Directory che si connettono da un endpoint esterno al firewall aziendale. Il servizio Access Edge passa le richieste di accesso a un Director, se presente, o a un Front End Server per l'autenticazione. Il servizio Access Edge in sé non esegue alcuna autenticazione.
    
    > [!NOTE]
    > Il protocollo NTLM offre una minore protezione dagli attacchi rispetto a Kerberos, pertanto viene utilizzato il meno possibile da alcune organizzazioni. Di conseguenza, l'accesso a Skype for Business Server potrebbe essere limitato ai client o all'interno connessi tramite una connessione VPN o DirectAccess. 
  
- **Protocollo digest** per i cosiddetti utenti anonimi. Gli utenti anonimi sono utenti esterni che non dispongono di credenziali di Active Directory riconosciute, ma che sono stati invitati a una conferenza locale e sono in possesso di una chiave di conferenza valida. L'autenticazione del digest non viene utilizzata per altre interazioni client.
    
L'autenticazione di Skype for Business Server è costituita da due fasi:
  
1. Viene stabilita un'associazione di sicurezza tra il client e il server.
    
2. Il client e il server utilizzano l'associazione di sicurezza esistente per firmare i messaggi inviati e per verificare i messaggi ricevuti. I messaggi non autenticati provenienti da un client non vengono accettati quando viene abilitata l'autenticazione nel server.
    
L'attendibilità utente è associata a ogni messaggio originato da un utente e non all'identità dell'utente. Il server verifica in ogni messaggio la validità delle credenziali utente. Se le credenziali utente sono valide, il messaggio non riceve richieste di autenticazione non solo dal primo server che lo riceve, ma anche da tutti gli altri server del cloud di server trusted.
  
Gli utenti con credenziali valide emesse da un partner federato sono attendibili, ma è possibile che a causa di vincoli aggiuntivi non sia loro consentito di usufruire di tutti i privilegi accordati agli utenti interni.
  
I protocolli ICE e TURN utilizzano inoltre la richiesta di autenticazione del digest come descritto nella specifica RFC TURN IETF.
  
I certificati client forniscono un modo alternativo per l'autenticazione degli utenti da parte di Skype for Business Server. Invece di fornire un nome utente e una password, gli utenti dispongono di un certificato e della chiave privata corrispondente al certificato necessario per risolvere una richiesta di verifica crittografica. (Il certificato deve avere un nome soggetto o un nome alternativo del soggetto che identifichi l'utente e deve essere emesso da una CA radice attendibile dai server che eseguono Skype for Business Server, sia entro il periodo di validità del certificato e non sia stato revocato). Per essere autenticati, gli utenti devono solo digitare un PIN (Personal Identification Number). I certificati sono particolarmente utili per telefoni, cellulari e altri dispositivi in cui è difficile immettere un nome utente e una password.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Requisiti di crittografia a causa di ASP .NET 4,5 

A partire da Skype for Business Server 2015 CU5, AES non è supportato per ASP.NET 4,6 e potrebbe non essere possibile avviare l'app riunioni Skype. Se un client utilizza AES come valore di convalida della chiave del computer, sarà necessario reimpostare il valore della chiave del computer su SHA-1 o su un altro algoritmo supportato sul livello di sito dell'app riunioni Skype su IIS. Se necessario, vedere [gestione della configurazione di IIS 8,0 ASP.NET](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) per istruzioni.
  
Altri valori supportati sono:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  I valori AES, 3DES e MD5 non sono più consentiti, in quanto si trovavano in ASP.NET 4. [Miglioramenti alla crittografia in ASP.NET 4,5, PT. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) sono disponibili ulteriori dettagli.
  
