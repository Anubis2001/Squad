############################################################
# Dockerfile that builds a Squad Gameserver
############################################################
FROM cm2network/steamcmd:root

LABEL maintainer="marwan.mohamed@cloudvia.net"

ENV STEAMAPPID 403240
ENV STEAMAPP squad
ENV STEAMAPPDIR "/home/container/SquadGameServer/server1"

ENV STEAM_BETA_APP 774961
ENV STEAM_BETA_PASSWORD ""
ENV STEAM_BETA_BRANCH ""

ENV WORKSHOPID 393380
ENV MODPATH "/home/container/SquadGameServer/server1/SquadGame/Plugins/Mods"
ENV MODS "()"

COPY etc/entry.sh ${HOMEDIR}

#RUN set -x \
#	&& mkdir -p "/home/container/SquadGameServer" \
#	&& chmod 755 "${HOMEDIR}/entry.sh" "${STEAMAPPDIR}" \
#	&& chown "${USER}:${USER}" "${HOMEDIR}/entry.sh" "${STEAMAPPDIR}"

ENV PORT=7787 \
	QUERYPORT=27165 \
	RCONPORT=21114 \
	FIXEDMAXPLAYERS=80 \
	FIXEDMAXTICKRATE=50 \
	RANDOM=NONE

# Switch to user
USER ${USER}

WORKDIR ${HOMEDIR}

CMD ["bash", "SquadGameServer.sh"]

# Expose ports
EXPOSE 7787/udp \
	27165/tcp \
	27165/udp \
	21114/tcp \
	21114/udp
