{
  "experimental": {
    "clash_api": {
      "external_controller": "",
      "secret": ""
    },
    "debug": {
      "max_threads": null,
      "panic_on_fault": false
    },
    "cache_file": {
      "enabled": false,
      "path": "",
      "store_fakeip": true
    }
  },
  "log": {
    "disabled": false,
    "level": "info",
    "output": "",
    "timestamp": true
  },
  "ntp": {
    "enabled": false,
    "server": "time.windows.com",
    "server_port": 123,
    "interval": "12h",
    "detour": "direct_out"
  },
  "dns": {
    "final": "dns_final_out",
    "strategy": "ipv4_only",
    "independent_cache": true,
    "rules": [
      {
        "domain": [
          "v01.gutingting.com",
          "v02.gutingting.com"
        ],
        "server": "dns_outbound_out",
        "rewrite_ttl": 43200
      },
      {
        "rule_set": [
          "geosite:cn"
        ],
        "server": "dns_direct_out",
        "rewrite_ttl": 43200
      }
    ],
    "servers": [
      {
        "tag": "dns_outbound_out",
        "address": "local"
      },
      {
        "tag": "dns_direct_out",
        "address": "local"
      },
      {
        "tag": "dns_proxy_out",
        "address": "https://1.1.1.1/dns-query",
        "address_resolver": "dns_resolver_out",
        "detour": "direct_out"
      },
      {
        "tag": "dns_final_out",
        "address": "https://1.1.1.1/dns-query",
        "address_resolver": "dns_resolver_out",
        "detour": "selector_out"
      },
      {
        "tag": "dns_resolver_out",
        "address": "local"
      },
      {
        "tag": "dns_block_out",
        "address": "rcode://success"
      }
    ]
  },
  "inbounds": [
    {
      "type": "mixed",
      "tag": "mixed_in_direct",
      "set_system_proxy": false,
      "listen": "127.0.0.1",
      "listen_port": 3065,
      "sniff": true,
      "sniff_override_destination": false
    },
    {
      "type": "mixed",
      "tag": "mixed_in_forword",
      "set_system_proxy": false,
      "listen": "127.0.0.1",
      "listen_port": 3066,
      "sniff": true,
      "sniff_override_destination": false
    },
    {
      "type": "mixed",
      "tag": "mixed_in_rule",
      "set_system_proxy": false,
      "listen": "127.0.0.1",
      "listen_port": 3067,
      "sniff": true,
      "sniff_override_destination": false
    },
    {
      "type": "tun",
      "tag": "tun_in",
      "interface_name": "Karing TUN Network Adapter",
      "inet4_address": [
        "10.20.0.1/30"
      ],
      "inet6_address": null,
      "mtu": 9000,
      "auto_route": true,
      "strict_route": false,
      "stack": "gvisor",
      "platform": {
        "http_proxy": {
          "enabled": true,
          "server": "127.0.0.1",
          "server_port": 3067
        }
      },
      "include_package": null,
      "exclude_package": null,
      "udp_timeout": "15s",
      "sniff": true,
      "sniff_override_destination": false,
      "domain_strategy": "ipv4_only"
    }
  ],
  "outbounds": [
    {
      "server": "36.151.195.24",
      "server_port": 51377,
      "tag": "🇨🇳CN-36.151.195.24-0513",
      "type": "trojan",
      "password": "lNOcIAxy",
      "tls": {
        "enabled": true,
        "server_name": "36.151.195.24",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "59.3.3.161",
      "server_port": 443,
      "tag": "🇰🇷KR-59.3.3.161-0936",
      "type": "trojan",
      "password": "CMLiu",
      "tls": {
        "enabled": true,
        "server_name": "aliorg.filegear-sg.me",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      },
      "transport": {
        "type": "ws",
        "path": "/",
        "headers": {
          "Host": [
            "aliorg.filegear-sg.me"
          ]
        }
      }
    },
    {
      "server": "222.97.95.239",
      "server_port": 10443,
      "tag": "🇰🇷KR-222.97.95.239-0938",
      "type": "trojan",
      "password": "CMLiu",
      "tls": {
        "enabled": true,
        "server_name": "aliorg.filegear-sg.me",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      },
      "transport": {
        "type": "ws",
        "path": "/",
        "headers": {
          "Host": [
            "aliorg.filegear-sg.me"
          ]
        }
      }
    },
    {
      "server": "85.159.228.23",
      "server_port": 8443,
      "tag": "🇱🇻LV-85.159.228.23-0939",
      "type": "trojan",
      "password": "CMLiu",
      "tls": {
        "enabled": true,
        "server_name": "aliorg.filegear-sg.me",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      },
      "transport": {
        "type": "ws",
        "path": "/",
        "headers": {
          "Host": [
            "aliorg.filegear-sg.me"
          ]
        }
      }
    },
    {
      "server": "42.236.73.72",
      "server_port": 443,
      "tag": "🇨🇳CN-42.236.73.72-1076",
      "type": "trojan",
      "password": "fuck",
      "tls": {
        "enabled": true,
        "server_name": "www.zitian.cn",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "120.236.197.205",
      "server_port": 3389,
      "tag": "🇨🇳CN-120.236.197.205-1856",
      "type": "trojan",
      "password": "ba4fedf8c217c146",
      "tls": {
        "enabled": true,
        "server_name": "n2.gladns.com",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "v01.gutingting.com",
      "server_port": 20220,
      "tag": "🇨🇳CN-120.241.176.230-2133",
      "type": "trojan",
      "password": "f89390de-248e-4a5f-b50e-35be0cd965a1",
      "tls": {
        "enabled": true,
        "server_name": "v2jp01.fuqiangren.com",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "v01.gutingting.com",
      "server_port": 30050,
      "tag": "🇨🇳CN-120.241.176.230-2134",
      "type": "trojan",
      "password": "8cf18212-6899-4d09-9cdc-b7dd91cc4611",
      "tls": {
        "enabled": true,
        "server_name": "v2sg02.fuqiangren.com",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "120.226.39.25",
      "server_port": 19243,
      "tag": "🇨🇳CN-120.226.39.25-2144",
      "type": "trojan",
      "password": "0b2d98a4-25bc-3d9f-9694-9d1e929de8dd",
      "tls": {
        "enabled": true,
        "server_name": "120.226.39.25",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "v02.gutingting.com",
      "server_port": 30006,
      "tag": "🇨🇳CN-120.241.176.230-2167",
      "type": "trojan",
      "password": "261ccd4c-425d-43a2-bf2a-59c3d1f02e94",
      "tls": {
        "enabled": true,
        "server_name": "v2hgc02.fuqiangren.com",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "v02.gutingting.com",
      "server_port": 30054,
      "tag": "🇨🇳CN-120.241.176.230-2178",
      "type": "trojan",
      "password": "261ccd4c-425d-43a2-bf2a-59c3d1f02e94",
      "tls": {
        "enabled": true,
        "server_name": "v1jp01.fuqiangren.com",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "120.226.39.25",
      "server_port": 19240,
      "tag": "🇨🇳CN-120.226.39.25-2189",
      "type": "trojan",
      "password": "0b2d98a4-25bc-3d9f-9694-9d1e929de8dd",
      "tls": {
        "enabled": true,
        "server_name": "120.226.39.25",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "v02.gutingting.com",
      "server_port": 20223,
      "tag": "🇨🇳CN-120.241.176.230-2203",
      "type": "trojan",
      "password": "b504c643-d081-4c90-8f50-9b0bf0b0902d",
      "tls": {
        "enabled": true,
        "server_name": "v2sg01.fuqiangren.com",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "v02.gutingting.com",
      "server_port": 30052,
      "tag": "🇨🇳CN-120.241.176.230-2215",
      "type": "trojan",
      "password": "c1596d35-5f68-4cef-bf5f-ac0d2ab88b2f",
      "tls": {
        "enabled": true,
        "server_name": "v2th01.fuqiangren.com",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "v02.gutingting.com",
      "server_port": 30053,
      "tag": "🇨🇳CN-120.241.176.230-2216",
      "type": "trojan",
      "password": "c1596d35-5f68-4cef-bf5f-ac0d2ab88b2f",
      "tls": {
        "enabled": true,
        "server_name": "v2phl01.fuqiangren.com",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "120.226.39.25",
      "server_port": 19248,
      "tag": "🇨🇳CN-120.226.39.25-2226",
      "type": "trojan",
      "password": "0b2d98a4-25bc-3d9f-9694-9d1e929de8dd",
      "tls": {
        "enabled": true,
        "server_name": "120.226.39.25",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "120.226.39.25",
      "server_port": 19225,
      "tag": "🇨🇳CN-120.226.39.25-2229",
      "type": "trojan",
      "password": "0b2d98a4-25bc-3d9f-9694-9d1e929de8dd",
      "tls": {
        "enabled": true,
        "server_name": "120.226.39.25",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "server": "v01.gutingting.com",
      "server_port": 30002,
      "tag": "🇨🇳CN-120.241.176.230-2251",
      "type": "trojan",
      "password": "1957909a-4f2a-4d9c-99ad-119d45f052c1",
      "tls": {
        "enabled": true,
        "server_name": "v2tw01.fuqiangren.com",
        "insecure": true,
        "utls": {
          "enabled": true
        }
      }
    },
    {
      "type": "urltest",
      "tag": "urltest_out",
      "url": "https://www.gstatic.com/generate_204",
      "interval": "8h",
      "interrupt_exist_connections": false,
      "idle_timeout": "8h",
      "outbounds": [
        "🇨🇳CN-36.151.195.24-0513",
        "🇰🇷KR-59.3.3.161-0936",
        "🇰🇷KR-222.97.95.239-0938",
        "🇱🇻LV-85.159.228.23-0939",
        "🇨🇳CN-42.236.73.72-1076",
        "🇨🇳CN-120.236.197.205-1856",
        "🇨🇳CN-120.241.176.230-2133",
        "🇨🇳CN-120.241.176.230-2134",
        "🇨🇳CN-120.226.39.25-2144",
        "🇨🇳CN-120.241.176.230-2167",
        "🇨🇳CN-120.241.176.230-2178",
        "🇨🇳CN-120.226.39.25-2189",
        "🇨🇳CN-120.241.176.230-2203",
        "🇨🇳CN-120.241.176.230-2215",
        "🇨🇳CN-120.241.176.230-2216",
        "🇨🇳CN-120.226.39.25-2226",
        "🇨🇳CN-120.226.39.25-2229",
        "🇨🇳CN-120.241.176.230-2251"
      ]
    },
    {
      "type": "selector",
      "tag": "selector_out",
      "default": "urltest_out",
      "interrupt_exist_connections": false,
      "outbounds": [
        "urltest_out"
      ]
    },
    {
      "type": "direct",
      "tag": "direct_out"
    },
    {
      "type": "block",
      "tag": "block_out"
    },
    {
      "type": "dns",
      "tag": "dns_out"
    }
  ],
  "route": {
    "final": "selector_out",
    "find_process": true,
    "auto_detect_interface": true,
    "rules": [
      {
        "inbound": [
          "mixed_in_direct"
        ],
        "outbound": "direct_out"
      },
      {
        "inbound": [
          "mixed_in_forword"
        ],
        "outbound": "selector_out"
      },
      {
        "protocol": "dns",
        "outbound": "dns_out"
      },
      {
        "domain_suffix": [
          "ingest.sentry.io",
          "karing.app",
          "yacd.metacubex.one"
        ],
        "outbound": "direct_out"
      },
      {
        "domain_suffix": [
          "speed.cloudflare.com"
        ],
        "outbound": "selector_out"
      },
      {
        "rule_set": [
          "geosite:cn"
        ],
        "outbound": "direct_out"
      },
      {
        "rule_set": [
          "geoip:cn"
        ],
        "outbound": "direct_out"
      },
      {
        "ip_is_private": true,
        "outbound": "direct_out"
      }
    ],
    "rule_set": [
      {
        "tag": "geosite:cn",
        "type": "remote",
        "format": "binary",
        "url": "https://github.com/KaringX/karing-ruleset/raw/sing/geo/geosite/cn.srs",
        "download_detour": "selector_out"
      },
      {
        "tag": "geoip:cn",
        "type": "remote",
        "format": "binary",
        "url": "https://github.com/KaringX/karing-ruleset/raw/sing/geo/geoip/cn.srs",
        "download_detour": "selector_out"
      }
    ]
  }
}
