Cahier des Charges Détaillé pour la Reprise du Développement CaniCoach IA
Objectif Principal : Développer une application mobile web (PWA) "CaniCoach IA" qui incarne la méthode d'éducation canine de Tony Silvestre (Esprit Dog), offrant une guidance hyper-personnalisée, cohérente et déculpabilisante aux propriétaires de chiots et de chiens adultes. L'objectif est de fournir un "coach de mise en pratique" instantané, complémentaire aux formations existantes, pour résoudre les problèmes comportementaux quotidiens et construire une relation de confiance durable.
Introduction : Rappel de la Vision et de la Proposition de Valeur Unique
Le marché de la Pet Tech est en pleine croissance, porté par l'humanisation des animaux de compagnie et l'adoption technologique. Les propriétaires francophones sont submergés par des informations contradictoires et la peur de "mal faire". CaniCoach IA se positionne comme le remède à cette anxiété informationnelle.
Philosophie Esprit Dog : L'éducation efficace découle d'une compréhension profonde de la psychologie et des besoins du chiot, au-delà de la simple obéissance. Le cadre de vie doit être clair, avec un équilibre entre ce qui est autorisé ("Oui") et ce qui est interdit ("Non"), le "Non" étant un outil de navigation nécessitant un "plan B". Le jeu est le pilier central de l'apprentissage et de la relation.
Proposition de Valeur Unique (USP) : "CaniCoach IA est le seul coach canin virtuel qui met toute l'expertise et la philosophie bienveillante de Tony Silvestre (Esprit Dog) dans votre poche. Obtenez des conseils hyper-personnalisés, cohérents et déculpabilisants, 24/7, pour construire la relation de confiance que vous avez toujours voulue avec votre chien."
I. État Actuel du Projet et Technologies Existantes
Le projet est une maquette avancée, visuellement impressionnante et fonctionnelle.
• Frontend : Application React/TypeScript avec Vite, avec une refonte UX/UI majeure par Claude AI (design mobile-first, palette de couleurs harmonisée, arrondis, ombres, espacements, emojis, réactivité tactile, accessibilité, responsive design).
• Backend / Bases de Données : Supabase est intégré pour l'authentification, la gestion des profils utilisateurs et chiens, et une base de connaissances.
• Fonctionnalités Implémentées :
    ◦ Authentification utilisateur (email via Magic Link, Google OAuth, déconnexion).
    ◦ Gestion des profils utilisateur (nom d'utilisateur, site web).
    ◦ Gestion des profils chiens (CRUD : création, lecture, modification, suppression) avec Row Level Security (RLS) pour la sécurité des données.
    ◦ Chatbot conversationnel (interface de chat, recherche de connaissances basée sur mots-clés dans knowledge_base, affichage Markdown, simulation des infos du chien).
    ◦ Simulation du modèle économique (essai gratuit limité à 5 interactions, affichage du paywall, réinitialisation pour la démo).
II. Fonctionnalités Clés à Continuer / Développer (Priorité Haute)
1. Gestion des Profils Chiens :
    ◦ Compléter les champs du profil chien : Ajouter les champs suivants pour chaque chien : photo (upload), provenance (élevage, refuge, particulier...), problèmes de santé connus, passé (traumatismes, etc.).
    ◦ Multi-profils pour les abonnés : Permettre aux utilisateurs avec un abonnement actif d'ajouter et de gérer plusieurs profils de chiens. Le code existant (srcDogManager.tsx) gère déjà la logique CRUD pour plusieurs chiens liés à un owner_id.
2. Chatbot Conversationnel (Cœur de l'IA) :
    ◦ Amélioration de la recherche de connaissances : Optimiser l'extraction des mots-clés et la logique de recherche dans la knowledge_base pour une pertinence accrue. Utiliser des techniques plus avancées si nécessaire (e.g., recherche sémantique, embeddings) pour mieux interpréter l'intention de l'utilisateur.
    ◦ Intégration profonde du profil du chien : Le chatbot doit utiliser les informations du dogProfile (nom, race, date de naissance, problèmes de santé, passé) pour personnaliser les réponses, au-delà de la simple affichage. Par exemple, si le chien a des "problèmes de propreté connus", la réponse sur la propreté doit en tenir compte.
    ◦ Intégration du ton et des analogies Esprit Dog : L'IA doit être entraînée à adopter le ton, le style de langage et les analogies spécifiques de Tony Silvestre et de la méthode Esprit Dog (e.g., "dépôt de confiance", "fête sensorielle", "éponge sensorielle", "ministre du bonheur", "pire/meilleur des endroits").
    ◦ Hyper-personnalisation basée sur le profil du maître : L'IA doit tenter de déduire l'état émotionnel du maître (stress, frustration, découragement) à partir de son langage dans les requêtes et adapter sa réponse pour être non seulement techniquement correcte, mais aussi psychologiquement pertinente et déculpabilisante.
3. Gestion de l'Abonnement et Paywall :
    ◦ Implémentation de Stripe : Intégrer une solution de paiement sécurisée via Stripe pour les abonnements Mensuel et Annuel.
    ◦ Page de Statut d'Abonnement : Développer une page où l'utilisateur peut voir son statut actuel (Essai, Mensuel, Annuel), gérer ses informations de paiement et résilier son abonnement facilement.
    ◦ Déclenchement du Paywall : Assurer que le paywall se déclenche fidèlement au modèle économique : après la résolution intégrale du premier problème ou si l'utilisateur tente d'aborder un deuxième sujet. La simulation actuelle de 5 interactions est une base.
III. Fonctionnalités Innovantes et d'Engagement (Priorité Moyenne)
1. Journal de Progrès ("Timeline") :
    ◦ Développer une section où l'utilisateur peut documenter son parcours avec son chien via des entrées de journal (texte court, photo).
    ◦ L'objectif est de créer un lien émotionnel et de visualiser les progrès pour augmenter la motivation et la rétention.
2. Défis Hebdomadaires :
    ◦ Mettre en place un système de notifications push hebdomadaires (ex: chaque lundi) avec un défi simple et ludique lié à l'éducation (ex: "Apprenez 'le toucher' à votre chien !").
    ◦ L'objectif est de maintenir l'engagement et d'enrichir la relation maître-chien.
3. Rappels d'Étapes Clés (Proactifs et Contextuels) :
    ◦ Utiliser la date de naissance du chien (via le profil) pour envoyer des notifications personnalisées basées sur son âge.
    ◦ Exemples : "Rocky a maintenant 4 mois, période critique pour la socialisation. Avez-vous pensé à lui faire rencontrer des congénères calmes cette semaine ?" ou "Votre chiot entre dans l'adolescence ! Attendez-vous à des régressions, c'est normal".
    ◦ L'objectif est d'anticiper les besoins et de montrer une intelligence proactive de l'application.
IV. Intégration de la Base de Connaissances Esprit Dog (Cœur du Contenu)
La base de connaissances de l'IA doit être exhaustive et fidèlement alignée avec les principes Esprit Dog tirés des Donnees_01.txt et Donnees_02.txt.
• Principes Fondamentaux :
    ◦ Période d'imprégnation (0-4 mois) : Insister sur l'importance cruciale de la socialisation précoce et de l'exposition au monde, même avant la fin des vaccins (en évitant les zones à risque élevé).
    ◦ Leadership vs. Dominance : Redéfinir le leadership comme un guide fiable, cohérent et admirable, et non comme une domination physique.
    ◦ Gestion des émotions : Apprendre au chiot à gérer la frustration et l'excitation par le renoncement et le jeu contrôlé. Ne pas réconforter la peur, mais rester neutre.
    ◦ Jeu comme pilier : Mettre en avant le jeu comme outil d'apprentissage de l'autocontrôle, de la gestion de la morsure et du renforcement de la relation.
    ◦ Récompenses : Utilisation intelligente des récompenses (voix, caresse, jouet, friandise), avec un timing précis. La voix comme récompense la plus rapide et polyvalente.
• Thèmes Majeurs (pour enrichir la knowledge_base et les réponses) :
    ◦ Arrivée du Chiot : Création d'un environnement de confiance, observation de la mère pour le tempérament, adéquation maître/chiot.
    ◦ Accessoires : Prioriser le simple et fonctionnel (longe, collier plat, jouets d'occupation/interaction) ; proscrire harnais quotidiens, laisses courtes pour chiots, colliers coercitifs.
    ◦ Préparation de la Maison : Sécurité, limitation de l'accès pour la propreté, jouets d'occupation prêts, zones définies.
    ◦ Balades : Ne pas se limiter au "tour du pâté de maison" ; varier les lieux (basse, moyenne, haute stimulation) pour la socialisation et la dépense mentale/physique. Importance de la longe et du suivi naturel.
    ◦ Vétérinaire : Choisir un vétérinaire aligné sur la socialisation précoce ; poser les bonnes questions.
    ◦ Conditions d'accueil : Disponibilité du maître (congés), sorties fréquentes pour la propreté et la solitude.
    ◦ Premier Jour : Dépôt de confiance, calme, exploration limitée, pas de dressage.
    ◦ Sommeil la nuit : Faire dormir le chiot dans la chambre du maître les premières nuits pour prévenir l'anxiété de séparation et accélérer la propreté.
    ◦ Voyage éleveur => maison : Utilisation d'un contenant adapté (caisse), conduite douce, cohérence.
    ◦ Place de l'enfant dans l'éducation : L'enfant comme "ministre du bonheur", les parents garants du cadre ; ne pas déléguer la punition.
    ◦ Propreté : Anticipation, fréquence des sorties, récompense immédiate à l'extérieur. Gestion des accidents (pas de punition après coup). Pipi émotionnel (ne pas punir). Rejeter l'utilisation de la cage pour la propreté. Laisser l'eau à disposition en permanence. Gérer le chiot qui ne fait pas en balade. Proscrire les tapis d'aisance/journaux.
    ◦ Solitude : Apprentissage graduel par micro-absences, dé-dramatisation des départs/retours, association positive avec jouet d'occupation, dépense énergétique avant l'absence. La solitude nocturne est une conséquence de la sécurité diurne.
    ◦ Destruction : Symptôme d'un besoin non satisfait (ennui, anxiété, exploration, poussée dentaire). Prévention par dépense physique/mentale et besoin masticatoire comblé. Utilisation stratégique des jouets (occupation vs. interaction). Redirection avec "Non" et "Plan B". Proscrire les répulsifs et la punition différée.
    ◦ Socialisation : Exposer positivement le chiot à tous stimuli (autres chiens, humains, lieux, bruits) durant la période d'imprégnation. Attitude du maître (calme, référent sécurisant). Rejeter les écoles de chiots "100% chiots" ; préférer celles avec adultes régulateurs. Laisser les chiens communiquer naturellement. Cohabitation chien-chat par présentation calme et échappatoire pour le chat. Pratiquer sous haute stimulation progressivement.
    ◦ Comportements Spécifiques :
        ▪ Simulation de l'acte sexuel : Excitation/stress, pas dominance ; interrompre et rediriger.
        ▪ Moments de folie ("Zoomies") : Décharge d'énergie normale ; sécuriser, ne pas participer, prévenir par dépense.
        ▪ Aboiements : Comprendre la cause (alerte, anxiété, frustration, ennui) ; traiter la cause ; proscrire les colliers anti-aboiement.
        ▪ Sauts : Joie/recherche de bonheur ; offrir le bonheur de manière contrôlée plutôt qu'ignorer ou punir physiquement.
    ◦ Manipulations dans le panier : Désacraliser le panier par des manipulations positives pour prévenir la protection de ressources.
    ◦ Relation forte : Basée sur confiance, complicité, jeu et balades ; maître guide fiable.
    ◦ Apprentissage du prénom : Uniquement pour capter l'attention, toujours associé positivement ; ne jamais utiliser pour gronder.
    ◦ Repas : Moment calme ; désacraliser la gamelle par l'exercice de la main pour prévenir la protection de ressources. Gérer le refus de manger par la règle des "10 minutes" après consultation vétérinaire. L'ordre des repas (maître vs. chien) est un mythe sans impact hiérarchique.
    ◦ Jeu : Le jeu est un pilier ; pas de "jeux interdits", seulement des jeux mal encadrés. Permettre au chien de gagner aux jeux de tirage pour renforcer sa confiance et son plaisir.
    ◦ Règles du "Non" et des Punitions : Le "Non" efficace doit toujours être suivi d'un "plan B". Proscrire absolument les punitions liées à la propreté (nez dans l'excrément), la soumission physique ("alpha roll") et l'isolement comme punition.
    ◦ Mordillements : Comportement normal d'exploration ; encadrer par redirection vers jouets autorisés et apprentissage du contrôle de la mâchoire ("Aïe!") pendant le jeu.
    ◦ Escaliers : Mythe ; risque lié aux impacts répétés, pas à la montée/descente calme ; porter si possible, mais ne pas paniquer.
    ◦ Agrippage (laisse, pantalons) : Souvent signe d'un trop-plein d'énergie ; solution par la dépense et la gestion des émotions, non par la punition.
    ◦ Dressage : Les ordres servent la liberté et l'intégration du chien (ex: rappel pour balades en liberté, "au panier" pour les sorties). Apprentissage par leurre et renforcement positif ("assis", "couché"). "Au panier" rendu positif. Rappel par renforcement positif du retour au maître. Marche en laisse détendue comme résultat d'une éducation globale (dépense, désensibilisation, gestion des émotions). "Prends" / "Donne" par troc positif pour éviter la protection de ressources.
    ◦ Renforcement des comportements naturels positifs : "Attraper son chien en train de bien faire" et le récompenser pour ses bons comportements spontanés (ex: se coucher calmement).
V. Ligne Directrice UX/UI et Stratégie de Ton
• Cohérence Visuelle : Maintenir et affiner la cohérence "mobile-first" et le design moderne (couleurs harmonisées, arrondis, ombres, espacements, emojis) déjà implémentés par Claude AI.
• Ton de Communication : L'IA doit adopter un ton déculpabilisant, encourageant, fiable et cohérent avec la philosophie Esprit Dog. Éviter tout langage accusateur ou jargon complexe. Le langage doit refléter le partenariat et la bienveillance.
• Accessibilité et Réactivité : S'assurer de la réactivité tactile et de l'accessibilité continue de l'application sur diverses tailles d'écrans mobiles.
VI. Optimisation et Performance
• Performance : Prioriser un chargement rapide des données, une fluidité de l'interface utilisateur et une réactivité du chatbot.
• Robustesse : Renforcer la gestion des erreurs côté client et serveur, assurer la sécurité des données utilisateur via les politiques RLS de Supabase et les bonnes pratiques de développement.
• Testabilité : Structurer le code pour faciliter les tests unitaires, d'intégration et end-to-end, en prévision des futures phases de développement et de maintenance.
