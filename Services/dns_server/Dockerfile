FROM debian:buster

# Mise à jour des paquets et installation de Bind9
RUN apt-get update && \
    apt-get install -y bind9 && \
    rm -rf /var/lib/apt/lists/*

# Exposer le port DNS (53)
EXPOSE 53/udp

# Copier la configuration Bind9
COPY named.conf.options /etc/bind/named.conf.options
COPY named.conf.local /etc/bind/named.conf.local
COPY db.local /etc/bind/db.local

# Commande de démarrage
CMD ["/usr/sbin/named", "-g", "-c", "/etc/bind/named.conf"]
