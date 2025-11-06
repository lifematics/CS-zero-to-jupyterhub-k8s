# FIXME: use of alpine:3.19 makes iptables work in "nf_tables" mode instead of
#        "legacy" mode, and then our init container breaks.
#
#        ref: https://github.com/jupyterhub/zero-to-jupyterhub-k8s/issues/3368
#
FROM alpine:3.18

# VULN_SCAN_TIME=2025-02-17_05:04:56

#RUN apk add --no-cache iptables

# Use iptables-legacy as workaround.
# cf. https://github.com/tailscale/tailscale/issues/10540
RUN apk add --no-cache ca-certificates iptables
RUN update-alternatives --set iptables /usr/sbin/iptables-legacy || true
RUN update-alternatives --set ip6tables /usr/sbin/ip6tables-legacy || true
