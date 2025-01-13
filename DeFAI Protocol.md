# DeFAI Protocol

- CREATE_TOKEN

    **Description:** Create and deploy new tokens through DODO platform, supporting customizable token parameters such as supply, name, symbol, decimal places, burn mechanism, trading fees and supply increase option

    **Keywords:** create token on dodo, deploy token dodo, mint new token, launch token, create cryptocurrency, token creation dodo, issue token, deploy smart contract, create erc20, create bep20, token generator, dodo token deploy, new token launch, token deployment, custom token creation, create digital currency, token minting, smart token creation, token issuance dodo, launch cryptocurrency, generate token, create token contract, token creation platform, token launch dodo, deploy new token

    ```tsx
    {
                "action": "CREATE_TOKEN",
                "network": "1",
                "inputs": [
                    {
                        "name": "tokenSymbol",
                        "type": "string",
                        "default": ""
                    },
                    {
                        "name": "tokenSupply",
                        "type": "number",
                        "default": "1_000_000_000"
                    },
                    {
                        "name": "tokenName",
                        "type": "string",
                        "default": ""
                    },
                    {
                        "name": "tokenDecimal",
                        "type": "number",
                        "default": "18"
                    },
                    {
                        "name": "burnRate",
                        "type": "number",
                        "default": "0"
                    },
                    {
                        "name": "tradingFees",
                        "type": "number",
                        "default": "0"
                    },
                    {
                        "name": "mintAble",
                        "type": "boolean",
                        "default": "false"
                    },
                    {
                        "name": "devBuy",
                        "type": "number",
                        "default": "0"
                    }
                ],
                "outputs": [
                    {
                        "name": "mintAddress",
                        "type": "string"
                    }
                ],
                "protocol": {
                    "DODO_Mintable": {
                        "contract": "0x7466C6FE28180c33e2a35989FD6833C8dD5A7E16",
                        "function": "createCustomMintableERC20"
                    }, //use this contract and function when the mintAble is true
                    "DODO_Std": {
                        "contract": "0x7466C6FE28180c33e2a35989FD6833C8dD5A7E16",
                        "function": "createStdERC20"
                    }, //use this contract and function when the mintAble is true & tradingFees is 0 & burnRate is 0
                    "DODO_Custom": {
                        "contract": "0x7466C6FE28180c33e2a35989FD6833C8dD5A7E16",
                        "function": "createCustomERC20"
                    }
                } // if mintable is ture --> "createCustomMintableERC20";if burn or tradingfees is ture --> "createCustomERC20" ; if all is fulse --> "createStdERC20"//
            },
    ```

- SWAP_TOKEN

    **Description:** Exchange tokens using decentralized exchanges (DEX) and aggregators, supporting multi-chain swaps with best route finding, optimal slippage settings, price impact calculations, and MEV protection across various liquidity sources and trading pairs

    **Keywords:** swap tokens, exchange crypto, trade tokens, token swap, dex swap, swap eth, swap cryptocurrency, exchange tokens, crypto swap, swap coins, token exchange, trade cryptocurrency, swap digital assets, dex trade, token trading, swap crypto assets, exchange pairs, swap trading pairs, defi swap, token conversion, swap on uniswap, pancakeswap exchange, sushiswap trade, trade on dex, best rate swap

    ```tsx
    {
                "action": "SWAP_TOKEN",
                "network": "1",
                "inputs": [
                    {
                        "name": "inputToken",
                        "type": "string",
                        "default": ""
                    },
                    {
                        "name": "inputNetwork",
                        "type": "string",
                        "default": ""
                    },
                    {
                        "name": "outputToken",
                        "type": "string",
                        "default": ""
                    },
                    {
                        "name": "outputNetwork",
                        "type": "string",
                        "default": ""
                    },
                    {
                        "name": "amount",
                        "type": "string",
                        "default": ""
                    },
                    {
                        "name": "slippage",
                        "type": "string",
                        "default": ""
                    },
                    {
                        "name": "prioritizationFee",
                        "type": "string",
                        "default": ""
                    }
                ],
                "outputs": [
                    {
                        "name": "success",
                        "type": "boolean"
                    }
                ],
                "protocol": {
                    "name": "uniswap"
                    "quote": "https://interface.gateway.uniswap.org/v2/quote"
                }
            },
    ```

- BRIDGE

    **Description:** Transfer tokens between different blockchain networks using cross-chain bridge protocols, supporting multiple token types (ERC20, NFTs) and chains (Ethereum, BSC, Polygon, etc.)

    **Keywords:** bridge tokens, cross chain transfer, bridge crypto, token bridge, cross chain bridge, bridge eth, bridge bnb, bridge assets, blockchain bridge, bridge cryptocurrency, bridge to polygon, bridge to bsc, cross chain swap, bridge to arbitrum, bridge to optimism, bridge to l2, chain transfer, bridge digital assets, cross chain movement, bridge wallet, token bridging, bridge network transfer, bridge to mainnet, bridge coins, network bridge

    ```tsx
    {
                "action": "BRIDGE",
                "network": "1",
                "inputs": [
                    {
                        "name": "inputToken",
                        "type": "string",
                        "default": ""
                    },
                    {
                        "name": "inputNetwork",
                        "type": "string",
                        "default": ""
                    },
                    {
                        "name": "outputToken",
                        "type": "string",
                        "default": ""
                    },
                    {
                        "name": "outputNetwork",
                        "type": "string",
                        "default": ""
                    },
                    {
                        "name": "amount",
                        "type": "string",
                        "default": ""
                    },
                    {
                        "name": "toAddress",
                        "type": "string",
                        "default": ""
                    }
                ],
                "outputs": [
                    {
                        "name": "success",
                        "type": "boolean"
                    }
                ],
                "protocol": {
                    "name": "LAYERSWAP"
                    "quote": "https://api.layerswap.io/api/v2/swaps"
                }
            },
    ```

- LENDING
    - LENDING_DEPOSIT

        **Description:** Deposit tokens into DeFi lending protocols as collateral, enabling interest earning and borrowing capabilities, with customizable deposit parameters including interest rate types, deposit terms, and automated yield generation through lending markets

        **Keywords:** deposit tokens, supply collateral, deposit crypto, lend assets, supply lending, deposit for yield, lending deposit, supply tokens, deposit to earn, lending supply, provide collateral, deposit assets, supply to lend, deposit cryptocurrency, lending pool deposit, supply interest, deposit to lend, lending market supply, yield deposit, collateral supply

        ```tsx
        {
                    "action": "LENDING_DEPOSIT",
                    "network": "1",
                    "inputs": [
                        {
                            "name": "asset",
                            "type": "string",
                            "default": ""
                        },
                        {
                            "name": "amount",
                            "type": "string",
                            "default": ""
                        }
                    ],
                    "outputs": [
                        {
                            "name": "success",
                            "type": "boolean"
                        }
                    ],
                    "protocol": {
                    "name": "AAVE"
                    "depositETH":{
                    "functionName": "depositETH",
                    "contract": {
                        "42161": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0xecD4bd3121F9FD604ffaC631bF6d41ec12f1fafb"
                        },
                        "43114": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0x2DeC8BCE3471eD65B1bB558Fa28439D45bF446d0"
                        },
                        "8453": {
                            "pool": "0xA238Dd80C259a72e81d7e4664a9801593F98d1c5",
                            "address": "0x8be473dCfA93132658821E67CbEB684ec8Ea2E74"
                        },
                        "56": {
                            "pool": "0x6807dc923806fE8Fd134338EABCA509979a7e0cB",
                            "address": "0x326aB0868bD279382Be2DF5E228Cb8AF38649AB4"
                        },
                        "1": {
                            "pool": "0x87870Bca3F3fD6335C3F4ce8392D69350B4fA4E2",
                            "address": "0x893411580e590D62dDBca8a703d61Cc4A8c7b2b9"
                        },
                        "10": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0xe9E52021f4e11DEAD8661812A0A6c8627abA2a54"
                        },
                        "137": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0xC1E320966c485ebF2A0A2A6d3c0Dc860A156eB1B"
                        },
                        "534352": {
                            "pool": "0x11fCfe756c05AD438e312a7fd934381537D3cFfe",
                            "address": "0xFF75A4B698E3Ec95E608ac0f22A03B8368E05F5D"
                        }
                    }
                    }//if the token is native token use this contract list and function

                    "supply": {
                    "functionName": "supply",
                    "contract": {
                        "42161": {
                            "address": "0x794@a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xDA10009cBd5D07dd0CeCc66161FC93D7c9000da1",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x4a838a3Dac6633bB1fd932B6f356DecFCAf7803D",
                                    "STATA_TOKEN": "0xc91c5297d7E161aCC74b482aAfCc75B85cc0bfeD",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf97f4df75117a78c1A5a0DBb814Af92458539FB4",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x86E53CF1B870786351Da77A57575e79CB55812CB",
                                    "STATA_TOKEN": "0x27dE098EF2772386cBCf1a4c8BEb886368b7F9a9",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xDe25a88F87FEd9F8999fAbF6729dCB121893623C",
                                    "STATA_TOKEN": "0x0Bc9E52051f553E75550CA22C196bf132c52Cf0B",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC.e"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x2f2a2543B76A4166549F7aaB2e75Bef0aefC5B0f",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x6ce185860a4963106506C203335A2910413708e9",
                                    "STATA_TOKEN": "0x32B95Fbe04e5a51cF99FeeF4e57Cf7e3FC9c5A93",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x82aF49447D8a07e3bd95BD0d56f35241523fBab1",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x639Fe6ab55C921f74e7fac1ee960C0B6293ba612",
                                    "STATA_TOKEN": "0x352F3475716261dCC991Bd5F2aF973eB3D0F5878",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xFd086bC7CD5C481DCC9C85ebE478A1C0b69FCbb9",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x84dC1C52D7C340AA54B4e8799FBB31C3D28E67aD",
                                    "STATA_TOKEN": "0xb165a74407fE1e519d6bCbDeC1Ed3202B35a4140",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xba5DdD1f9d7F570dc94a51479a000E3BCE967196",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xaD1d5344AaDE45F43E596773Bcc4c423EAbdD034",
                                    "STATA_TOKEN": "0x1C0c8EcED17aE093b3C1a1a8fFeBE2E9513a9346",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "EURS": {
                                    "decimals": 2,
                                    "UNDERLYING": "0xD22a58f79e9481D1a88e00c343885A588b34b68B",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xA14d53bC1F1c0F31B4aA3BD109344E5009051a84",
                                    "STATA_TOKEN": "0x9a40747BE51185A416B181789B671E78a8d045dD",
                                    "logoURI": "https://app.aave.com/icons/tokens/eurs.svg",
                                    "symbol": "EURS"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5979D7b546E38E414F7E9822514be443A4800529",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x87fE1503beFBF98C35c7526B0c488d950F822C0F",
                                    "STATA_TOKEN": "0x7775d4Ae4Dbb79a624fB96AAcDB8Ca74F671c0DF",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "MAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x3F56e0c36d275367b8C502090EDF38289b3dEa0d",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x7a7cE08a1057723CCEDeA2462407427Ae33FFEb2",
                                    "STATA_TOKEN": "0xB4a0a2692D82301703B27082Cda45B083F68CAcE",
                                    "logoURI": "https://app.aave.com/icons/tokens/mai.svg",
                                    "symbol": "MAI"
                                },
                                "rETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xEC70Dcb4A1EFa46b8F2D97C310C9c4790ba5ffA8",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x256f33FC0110B1297f78f48524631D30B752480D",
                                    "STATA_TOKEN": "0x68235105d6d33A19369D24b746cb7481FB2b34fd",
                                    "logoURI": "https://app.aave.com/icons/tokens/reth.svg",
                                    "symbol": "rETH"
                                },
                                "LUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x93b346b6BC2548dA6A1E7d98E9a421B42541425b",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x341B110bDF665A20F0D5f84A92FcAF5EbeEBC629",
                                    "STATA_TOKEN": "0xDbB6314b5b07E63B7101844c0346309B79f8C20A",
                                    "logoURI": "https://app.aave.com/icons/tokens/lusd.svg",
                                    "symbol": "LUSD"
                                },
                                "USDCn": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xaf88d065e77c8cC2239327C5EDb3A432268e5831",
                                    "A_TOKEN": "0x724dc807b04555b71ed48a6896b6F41593b8C637",
                                    "S_TOKEN": "0xDC1fad70953Bb3918592b6fCc374fe05F5811B6a",
                                    "V_TOKEN": "0xf611aEb5013fD2c0511c9CD55c7dc5C1140741A6",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xDe25a88F87FEd9F8999fAbF6729dCB121893623C",
                                    "STATA_TOKEN": "0x7CFaDFD5645B50bE87d546f42699d863648251ad",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "FRAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x17FC002b466eEc40DaE837Fc4bE5c67993ddBd6F",
                                    "A_TOKEN": "0x38d693cE1dF5AaDF7bC62595A37D667aD57922e5",
                                    "S_TOKEN": "0x8a9FdE6925a839F6B1932d16B36aC026F8d3FbdB",
                                    "V_TOKEN": "0x5D557B07776D12967914379C71a1310e917C7555",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x06919EB75Bd6BA817D38CC70C1CA588ac7a01C10",
                                    "STATA_TOKEN": "0x89AEc2023f89E26Dbb7eaa7a98fe3996f9d112A8",
                                    "logoURI": "https://app.aave.com/icons/tokens/frax.svg",
                                    "symbol": "FRAX"
                                },
                                "ARB": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x912CE59144191C1204E64559FE8253a0e49E6548",
                                    "A_TOKEN": "0x6533afac2E7BCCB20dca161449A13A32D391fb00",
                                    "S_TOKEN": "0x6B4b37618D85Db2a7b469983C888040F7F05Ea3D",
                                    "V_TOKEN": "0x44705f578135cC5d703b4c9c122528C73Eb87145",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xb2A824043730FE05F3DA2efaFa1CBbe83fa548D6",
                                    "STATA_TOKEN": "0x9b5637d7952BC9fa2D693aAE51f3103760Bf2693",
                                    "logoURI": "https://app.aave.com/icons/tokens/arb.svg",
                                    "symbol": "ARB"
                                },
                                "weETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x35751007a407ca6FEFfE80b3cB397736D2cf4dbe",
                                    "A_TOKEN": "0x8437d7C167dFB82ED4Cb79CD44B7a32A1dd95c77",
                                    "S_TOKEN": "0x40B4BAEcc69B882e8804f9286b12228C27F8c9BF",
                                    "V_TOKEN": "0x3ca5FA07689F266e907439aFd1fBB59c44fe12f6",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x517276B5972C4Db7E88B9F76Ee500E888a2D73C3",
                                    "logoURI": "https://app.aave.com/icons/tokens/weeth.svg",
                                    "symbol": "weETH"
                                },
                                "GHO": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7dfF72693f6A4149b17e7C6314655f6A9F7c8B33",
                                    "A_TOKEN": "0xeBe517846d0F36eCEd99C735cbF6131e1fEB775D",
                                    "S_TOKEN": "0x687871030477bf974725232F764aa04318A8b9c8",
                                    "V_TOKEN": "0x18248226C16BF76c032817854E7C83a2113B4f06",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xB05984aD83C20b3ADE7bf97a9a0Cb539DDE28DBb",
                                    "logoURI": "https://app.aave.com/icons/tokens/gho.svg",
                                    "symbol": "GHO"
                                }
                            }
                        },
                        "43114": {
                            "address": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAIe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xd586E7F844cEa2F87f50152665BCbc2C279D8d70",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xf82da795727633aFA9BB0f1B08A87c0F6A38723f",
                                    "STATA_TOKEN": "0x02F3f6c8A432C1e49f3359d7d36887C25d8A5888",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI.e"
                                },
                                "LINKe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5947BB275c521040051D82396192181b413227A3",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x49ccd9ca821EfEab2b98c60dC60F518E765EDe9a",
                                    "STATA_TOKEN": "0x8B773Ab77Dff01985D438961dBCE58382a70cA52",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK.e"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xB97EF9Ef8734C71904D8002F8b6Bc66Dd9c48a6E",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xD8277249e871BE9A402fa286C2C5ec16046dC512",
                                    "STATA_TOKEN": "0xC509aB7bB4eDbF193b82264D499a7Fc526Cd01F4",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "WBTCe": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x50b7545627a5162F82A992c33b87aDc75187B218",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x2779D32d5166BAaa2B2b658333bA7e6Ec0C65743",
                                    "STATA_TOKEN": "0xE3C0f42EAF1a4BFe37CbA105e5463564BA7730aE",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC.e"
                                },
                                "WETHe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x49D5c2BdFfac6CE2BFdB6640F4F80f226bc10bAB",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x976B3D034E162d8bD72D6b9C989d545b839003b0",
                                    "STATA_TOKEN": "0xf8E24175D01653fd6AA203C2C17B1e4Dd1CA2731",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH.e"
                                },
                                "USDt": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x9702230A8Ea53601f5cD2dc00fDBc13d4dF4A8c7",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x39185f2236A6022b682e8BB93C040d125DA093CF",
                                    "STATA_TOKEN": "0x5525Ee69BC1e354B356864187De486fab5AD67d7",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDt"
                                },
                                "AAVEe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x63a72806098Bd3D9520cC43356dD78afe5D386D9",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x3CA13391E9fb38a75330fb28f8cc2eB3D9ceceED",
                                    "STATA_TOKEN": "0xac0746AfD13DEbe2a43a6c8745Fb83Fd2A2909cA",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE.e"
                                },
                                "WAVAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xB31f66AA3C1e785363F0875A1B74E27b85FD66c7",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x0A77230d17318075983913bC2145DB16C7366156",
                                    "STATA_TOKEN": "0x6A02C7a974F1F13A67980C80F774eC1d2eD8f98d",
                                    "logoURI": "https://app.aave.com/icons/tokens/wavax.svg",
                                    "symbol": "WAVAX"
                                },
                                "sAVAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x2b2C81e08f1Af8835a78Bb2A90AE924ACE0eA4bE",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xB2B332f27e4B7305649a228C31Ed9858c5a6bAD9",
                                    "STATA_TOKEN": "0x4F059cA8a2a5BF8895Ee731f2E901cCB769FB95f",
                                    "logoURI": "https://app.aave.com/icons/tokens/savax.svg",
                                    "symbol": "sAVAX"
                                },
                                "FRAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD24C2Ad096400B6FBcd2ad8B24E7acBc21A1da64",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x6208576378D06ce69A27987b7A524A9B15d499a4",
                                    "STATA_TOKEN": "0xA3c2ffE702F4cD265B2249AB5f84Fab81FFf6c73",
                                    "logoURI": "https://app.aave.com/icons/tokens/frax.svg",
                                    "symbol": "FRAX"
                                },
                                "MAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5c49b268c9841AFF1Cc3B0a418ff5c3442eE3F3b",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xCcC55Db26B78a19Dba1beE0066F9c1665575439A",
                                    "STATA_TOKEN": "0x08cC59E51BB0Bc322B4D251f7262dB864d6150ce",
                                    "logoURI": "https://app.aave.com/icons/tokens/mai.svg",
                                    "symbol": "MAI"
                                },
                                "BTCb": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x152b9d0FdC40C096757F570A51E494bd4b943E50",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x2779D32d5166BAaa2B2b658333bA7e6Ec0C65743",
                                    "STATA_TOKEN": "0x34d768cc830c32DcD743321c09A2A702651bF9a2",
                                    "logoURI": "https://app.aave.com/icons/tokens/btc.svg",
                                    "symbol": "BTC.b"
                                }
                            }
                        },
                        "8453": {
                            "address": "0xA238Dd80C259a72e81d7e4664a9801593F98d1c5",
                            "ASSETS": {
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4200000000000000000000000000000000000006",
                                    "A_TOKEN": "0xD4a0e0b9149BCee3C920d2E00b5dE09138fd8bb7",
                                    "S_TOKEN": "0xaED3b56FeA82E809665f02AcBcDEc0816c75f4d9",
                                    "V_TOKEN": "0x24e6e0795b3c7c71D965fCc4f371803d1c1DcA1E",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x71041dddad3595F9CEd3DcCFBe3D1F4b0a16Bb70",
                                    "STATA_TOKEN": "0x468973e3264F2aEba0417A8f2cD0Ec397E738898",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "cbETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x2Ae3F1Ec7F1F5012CFEab0185bfc7aa3cf0DEc22",
                                    "A_TOKEN": "0xcf3D55c10DB69f28fD1A75Bd73f3D8A2d9c595ad",
                                    "S_TOKEN": "0xa9dF5c62d16d3f496673F4d736852017b086eCA0",
                                    "V_TOKEN": "0x1DabC36f19909425f654777249815c073E8Fd79F",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x8e11Ad4531826ff47BD8157a2c705F5422Da6A61",
                                    "STATA_TOKEN": "0x16A004065dfb11276DcB29Dc03fb8A85f9A43C6e",
                                    "logoURI": "https://app.aave.com/icons/tokens/cbeth.svg",
                                    "symbol": "cbETH"
                                },
                                "USDbC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xd9aAEc86B65D86f6A7B5B1b0c42FFA531710b6CA",
                                    "A_TOKEN": "0x0a1d576f3eFeF75b330424287a95A366e8281D54",
                                    "S_TOKEN": "0xBBaDd47fbaFa9dE717FE203e4707DEB893C64654",
                                    "V_TOKEN": "0x7376b2F323dC56fCd4C191B34163ac8a84702DAB",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x978D8878b53Fbe40dab7D4AB47b97AB622FFeF9f",
                                    "STATA_TOKEN": "0x6fCe2756794128B1771324caA860965801DCbCdB",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdbc.svg",
                                    "symbol": "USDbC"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xc1CBa3fCea344f92D9239c08C0568f6F2F0ee452",
                                    "A_TOKEN": "0x99CBC45ea5bb7eF3a5BC08FB1B7E56bB2442Ef0D",
                                    "S_TOKEN": "0xfe742Fa2a84294E8316F05b17c05090Fc68B5105",
                                    "V_TOKEN": "0x41A7C3f5904ad176dACbb1D99101F59ef0811DC1",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x56038D3998C42db18ba3B821bD1EbaB9B678e657",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913",
                                    "A_TOKEN": "0x4e65fE4DbA92790696d040ac24Aa414708F5c0AB",
                                    "S_TOKEN": "0x03506214379aA86ad1176af71c260278cfa10B38",
                                    "V_TOKEN": "0x59dca05b6c26dbd64b5381374aAaC5CD05644C28",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x978D8878b53Fbe40dab7D4AB47b97AB622FFeF9f",
                                    "STATA_TOKEN": "0x4EA71A20e655794051D1eE8b6e4A3269B13ccaCc",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "weETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x04C0599Ae5A44757c0af6F9eC3b93da8976c150A",
                                    "A_TOKEN": "0x7C307e128efA31F540F2E2d976C995E0B65F51F6",
                                    "S_TOKEN": "0xCBEdA45432D5325585ACAD29244f113C237B6Cf0",
                                    "V_TOKEN": "0x8D2e3F1f4b38AA9f1ceD22ac06019c7561B03901",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0xFc4d1d7a8FD1E6719e361e16044b460737F12C44",
                                    "logoURI": "https://app.aave.com/icons/tokens/weeth.svg",
                                    "symbol": "weETH"
                                }
                            }
                        },
                        "56": {
                            "address": "0x326aB0868bD279382Be2DF5E228Cb8AF38649AB4",
                            "ASSETS": {
                                "Cake": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82",
                                    "A_TOKEN": "0x4199CC1F5ed0d796563d7CcB2e036253E2C18281",
                                    "S_TOKEN": "0x57e95511de39890D3e782df4b19F0D97A05DF64A",
                                    "V_TOKEN": "0xE20dBC7119c635B1B51462f844861258770e0699",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0xB6064eD41d4f67e353768aA239cA86f4F73665a1",
                                    "STATA_TOKEN": "0x3854354CE3681da1D7F550073061E92a4a7d1B27",
                                    "logoURI": "https://app.aave.com/icons/tokens/cake.svg",
                                    "symbol": "Cake"
                                },
                                "WBNB": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xbb4CdB9CBd36B01bD1cBaEBF2De08d9173bc095c",
                                    "A_TOKEN": "0x9B00a09492a626678E5A3009982191586C444Df9",
                                    "S_TOKEN": "0x5cc46d2b1103aB23CFD63eF8631480bbf4eB40FE",
                                    "V_TOKEN": "0x0E76414d433ddfe8004d2A7505d218874875a996",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x0567F2323251f0Aab15c8dFb1967E4e8A7D42aeE",
                                    "STATA_TOKEN": "0x436baCb4C66583de4Cb16e13a1A0D9A3075DE425",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbnb.svg",
                                    "symbol": "WBNB"
                                },
                                "BTCB": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7130d2A12B9BCbFAe4f2634d864A1Ee1Ce3Ead9c",
                                    "A_TOKEN": "0x56a7ddc4e848EbF43845854205ad71D5D5F72d3D",
                                    "S_TOKEN": "0x9Ef6D76740713C674A6e4f38B863E62D10965053",
                                    "V_TOKEN": "0x7b1E82F4f542fbB25D64c5523Fe3e44aBe4F2702",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x264990fbd0A4796A3E3d8E37C4d5F87a3aCa5Ebf",
                                    "STATA_TOKEN": "0x1F66b530084079d35478A069d9c4424F9c9C320c",
                                    "logoURI": "https://app.aave.com/icons/tokens/btcb.svg",
                                    "symbol": "BTCB"
                                },
                                "ETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x2170Ed0880ac9A755fd29B2688956BD959F933F8",
                                    "A_TOKEN": "0x2E94171493fAbE316b6205f1585779C887771E2F",
                                    "S_TOKEN": "0xa8327EE1858E06983af6690d24e77774807109d4",
                                    "V_TOKEN": "0x8FDea7891b4D6dbdc746309245B316aF691A636C",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x9ef1B8c0E4F7dc8bF5719Ea496883DC6401d5b2e",
                                    "STATA_TOKEN": "0x52077433fB7053D747E2846aD0C18ff5015C368E",
                                    "logoURI": "https://app.aave.com/icons/tokens/eth.svg",
                                    "symbol": "ETH"
                                },
                                "USDC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x8AC76a51cc950d9822D68b83fE1Ad97B32Cd580d",
                                    "A_TOKEN": "0x00901a076785e0906d1028c7d6372d247bec7d61",
                                    "S_TOKEN": "0xCcC260D9778F900eAd566Fa2E1D622E667677653",
                                    "V_TOKEN": "0xcDBBEd5606d9c5C98eEedd67933991dC17F0c68d",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0xaFcFF74AE956f4c23c27Db49659D4a7F350415C1",
                                    "STATA_TOKEN": "0x3906cDdfb781f02B21f21BD81ed7Fd8DC37075E1",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "USDT": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x55d398326f99059fF775485246999027B3197955",
                                    "A_TOKEN": "0xa9251ca9DE909CB71783723713B21E4233fbf1B1",
                                    "S_TOKEN": "0xB735D922a36d4337f561CE433594727e1bc8bD01",
                                    "V_TOKEN": "0xF8bb2Be50647447Fb355e3a77b81be4db64107cd",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x0F682319Ed4A240b7a2599A48C965049515D9bC3",
                                    "STATA_TOKEN": "0x0471D185cc7Be61E154277cAB2396cD397663da6",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "FDUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xc5f0f7b66764F6ec8C8Dff7BA683102295E16409",
                                    "A_TOKEN": "0x75bd1A659bdC62e4C313950d44A2416faB43E785",
                                    "S_TOKEN": "0x5543d347bfae77A5FF913e589aB6D6ad520f1C73",
                                    "V_TOKEN": "0xE628B8a123e6037f1542e662B9F55141a16945C8",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x60a117Fa5bAbee4d645884fB11E413Da4F893b6D",
                                    "STATA_TOKEN": "0x4d074aAa0821073dA827f7bf6a02cF905b394ed0",
                                    "logoURI": "https://app.aave.com/icons/tokens/fdusd.svg",
                                    "symbol": "FDUSD"
                                }
                            }
                        },
                        "1": {
                            "address": "0x87870Bca3F3fD6335C3F4ce8392D69350B4fA4E2",
                            "ASSETS": {
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2",
                                    "A_TOKEN": "0x4d5F47FA6A74757f35C14fD3a6Ef8E3C9BC514E8",
                                    "S_TOKEN": "0x102633152313C81cD80419b6EcF66d14Ad68949A",
                                    "V_TOKEN": "0xeA51d7853EEFb32b6ee06b1C12E6dcCA88Be0fFE",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x5f4eC3Df9cbd43714FE2740f5E3616155c5b8419",
                                    "STATA_TOKEN": "0x252231882FB38481497f3C767469106297c8d93b",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7f39C581F595B53c5cb19bD0b3f8dA6c935E2Ca0",
                                    "A_TOKEN": "0x0B925eD163218f6662a35e0f0371Ac234f9E9371",
                                    "S_TOKEN": "0x39739943199c0fBFe9E5f1B5B160cd73a64CB85D",
                                    "V_TOKEN": "0xC96113eED8cAB59cD8A66813bCB0cEb29F06D2e4",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xB4aB0c94159bc2d8C133946E7241368fc2F2a010",
                                    "STATA_TOKEN": "0x322AA5F5Be95644d6c36544B6c5061F072D16DF5",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x2260FAC5E5542a773Aa44fBCfeDf7C193bc2C599",
                                    "A_TOKEN": "0x5Ee5bf7ae06D1Be5997A1A72006FE6C607eC6DE8",
                                    "S_TOKEN": "0xA1773F1ccF6DB192Ad8FE826D15fe1d328B03284",
                                    "V_TOKEN": "0x40aAbEf1aa8f0eEc637E0E7d92fbfFB2F26A8b7B",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x230E0321Cf38F09e247e50Afc7801EA2351fe56F",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48",
                                    "A_TOKEN": "0x98C23E9d8f34FEFb1B7BD6a91B7FF122F4e16F5c",
                                    "S_TOKEN": "0xB0fe3D292f4bd50De902Ba5bDF120Ad66E9d7a39",
                                    "V_TOKEN": "0x72E95b8931767C79bA4EeE721354d6E99a61D004",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x736bF902680e68989886e9807CD7Db4B3E015d3C",
                                    "STATA_TOKEN": "0x73edDFa87C71ADdC275c2b9890f5c3a8480bC9E6",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x6B175474E89094C44Da98b954EedeAC495271d0F",
                                    "A_TOKEN": "0x018008bfb33d285247A21d44E50697654f754e63",
                                    "S_TOKEN": "0x413AdaC9E2Ef8683ADf5DDAEce8f19613d60D1bb",
                                    "V_TOKEN": "0xcF8d0c70c850859266f5C338b38F9D663181C314",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xaEb897E1Dc6BbdceD3B9D551C71a8cf172F27AC4",
                                    "STATA_TOKEN": "0xaf270C38fF895EA3f95Ed488CEACe2386F038249",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x514910771AF9Ca656af840dff83E8264EcF986CA",
                                    "A_TOKEN": "0x5E8C8A7243651DB1384C0dDfDbE39761E8e7E51a",
                                    "S_TOKEN": "0x63B1129ca97D2b9F97f45670787Ac12a9dF1110a",
                                    "V_TOKEN": "0x4228F8895C7dDA20227F6a5c6751b8Ebf19a6ba8",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x2c1d072e956AFFC0D435Cb7AC38EF18d24d9127c",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7Fc66500c84A76Ad7e9c93437bFc5Ac33E2DDaE9",
                                    "A_TOKEN": "0xA700b4eB416Be35b2911fd5Dee80678ff64fF6C9",
                                    "S_TOKEN": "0x268497bF083388B1504270d0E717222d3A87D6F2",
                                    "V_TOKEN": "0xBae535520Abd9f8C85E58929e0006A2c8B372F74",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x547a514d5e3769680Ce22B2361c10Ea13619e8a9",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "cbETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xBe9895146f7AF43049ca1c1AE358B0541Ea49704",
                                    "A_TOKEN": "0x977b6fc5dE62598B08C85AC8Cf2b745874E8b78c",
                                    "S_TOKEN": "0x82bE6012cea6D147B968eBAea5ceEcF6A5b4F493",
                                    "V_TOKEN": "0x0c91bcA95b5FE69164cE583A2ec9429A569798Ed",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x6243d2F41b4ec944F731f647589E28d9745a2674",
                                    "logoURI": "https://app.aave.com/icons/tokens/cbeth.svg",
                                    "symbol": "cbETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xdAC17F958D2ee523a2206206994597C13D831ec7",
                                    "A_TOKEN": "0x23878914EFE38d27C4D67Ab83ed1b93A74D4086a",
                                    "S_TOKEN": "0x822Fa72Df1F229C3900f5AD6C3Fa2C424D691622",
                                    "V_TOKEN": "0x6df1C1E379bC5a00a7b4C6e67A203333772f45A8",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xC26D4a1c46d884cfF6dE9800B6aE7A8Cf48B4Ff8",
                                    "STATA_TOKEN": "0x862c57d48becB45583AEbA3f489696D22466Ca1b",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "rETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xae78736Cd615f374D3085123A210448E74Fc6393",
                                    "A_TOKEN": "0xCc9EE9483f662091a1de4795249E24aC0aC2630f",
                                    "S_TOKEN": "0x1d1906f909CAe494c7441604DAfDDDbD0485A925",
                                    "V_TOKEN": "0xae8593DD575FE29A9745056aA91C4b746eee62C8",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x5AE8365D0a30D67145f0c55A08760C250559dB64",
                                    "logoURI": "https://app.aave.com/icons/tokens/reth.svg",
                                    "symbol": "rETH"
                                },
                                "LUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5f98805A4E8be255a32880FDeC7F6728C6568bA0",
                                    "A_TOKEN": "0x3Fe6a295459FAe07DF8A0ceCC36F37160FE86AA9",
                                    "S_TOKEN": "0x37A6B708FDB1483C231961b9a7F145261E815fc3",
                                    "V_TOKEN": "0x33652e48e4B74D18520f11BfE58Edd2ED2cEc5A2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x9eCdfaCca946614cc32aF63F3DBe50959244F3af",
                                    "STATA_TOKEN": "0xDBf5E36569798D1E39eE9d7B1c61A7409a74F23A",
                                    "logoURI": "https://app.aave.com/icons/tokens/lusd.svg",
                                    "symbol": "LUSD"
                                },
                                "CRV": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD533a949740bb3306d119CC777fa900bA034cd52",
                                    "A_TOKEN": "0x7B95Ec873268a6BFC6427e7a28e396Db9D0ebc65",
                                    "S_TOKEN": "0x90D9CD005E553111EB8C9c31Abe9706a186b6048",
                                    "V_TOKEN": "0x1b7D3F4b3c032a5AE656e30eeA4e8E1Ba376068F",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xCd627aA160A6fA45Eb793D19Ef54f5062F20f33f",
                                    "logoURI": "https://app.aave.com/icons/tokens/crv.svg",
                                    "symbol": "CRV"
                                },
                                "MKR": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9f8F72aA9304c8B593d555F12eF6589cC3A579A2",
                                    "A_TOKEN": "0x8A458A9dc9048e005d22849F470891b840296619",
                                    "S_TOKEN": "0x0496372BE7e426D28E89DEBF01f19F014d5938bE",
                                    "V_TOKEN": "0x6Efc73E54E41b27d2134fF9f98F15550f30DF9B1",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xec1D1B3b0443256cc3860e24a46F108e699484Aa",
                                    "logoURI": "https://app.aave.com/icons/tokens/mkr.svg",
                                    "symbol": "MKR"
                                },
                                "SNX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xC011a73ee8576Fb46F5E1c5751cA3B9Fe0af2a6F",
                                    "A_TOKEN": "0xC7B4c17861357B8ABB91F25581E7263E08DCB59c",
                                    "S_TOKEN": "0x478E1ec1A2BeEd94c1407c951E4B9e22d53b2501",
                                    "V_TOKEN": "0x8d0de040e8aAd872eC3c33A3776dE9152D3c34ca",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xDC3EA94CD0AC27d9A86C180091e7f78C683d3699",
                                    "logoURI": "https://app.aave.com/icons/tokens/snx.svg",
                                    "symbol": "SNX"
                                },
                                "BAL": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xba100000625a3754423978a60c9317c58a424e3D",
                                    "A_TOKEN": "0x2516E7B3F76294e03C42AA4c5b5b4DCE9C436fB8",
                                    "S_TOKEN": "0xB368d45aaAa07ee2c6275Cb320D140b22dE43CDD",
                                    "V_TOKEN": "0x3D3efceb4Ff0966D34d9545D3A2fa2dcdBf451f2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xdF2917806E30300537aEB49A7663062F4d1F2b5F",
                                    "logoURI": "https://app.aave.com/icons/tokens/bal.svg",
                                    "symbol": "BAL"
                                },
                                "UNI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x1f9840a85d5aF5bf1D1762F925BDADdC4201F984",
                                    "A_TOKEN": "0xF6D2224916DDFbbab6e6bd0D1B7034f4Ae0CaB18",
                                    "S_TOKEN": "0x2FEc76324A0463c46f32e74A86D1cf94C02158DC",
                                    "V_TOKEN": "0xF64178Ebd2E2719F2B1233bCb5Ef6DB4bCc4d09a",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x553303d460EE0afB37EdFf9bE42922D8FF63220e",
                                    "logoURI": "https://app.aave.com/icons/tokens/uni.svg",
                                    "symbol": "UNI"
                                },
                                "LDO": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5A98FcBEA516Cf06857215779Fd812CA3beF1B32",
                                    "A_TOKEN": "0x9A44fd41566876A39655f74971a3A6eA0a17a454",
                                    "S_TOKEN": "0xa0a5bF5781Aeb548db9d4226363B9e89287C5FD2",
                                    "V_TOKEN": "0xc30808705C01289A3D306ca9CAB081Ba9114eC82",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xb01e6C9af83879B8e06a092f0DD94309c0D497E4",
                                    "logoURI": "https://app.aave.com/icons/tokens/ldo.svg",
                                    "symbol": "LDO"
                                },
                                "ENS": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xC18360217D8F7Ab5e7c516566761Ea12Ce7F9D72",
                                    "A_TOKEN": "0x545bD6c032eFdde65A377A6719DEF2796C8E0f2e",
                                    "S_TOKEN": "0x7617d02E311CdE347A0cb45BB7DF2926BBaf5347",
                                    "V_TOKEN": "0xd180D7fdD4092f07428eFE801E17BC03576b3192",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x5C00128d4d1c2F4f652C267d7bcdD7aC99C16E16",
                                    "logoURI": "https://app.aave.com/icons/tokens/ens.svg",
                                    "symbol": "ENS"
                                },
                                "ONE_INCH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x111111111117dC0aa78b770fA6A738034120C302",
                                    "A_TOKEN": "0x71Aef7b30728b9BB371578f36c5A1f1502a5723e",
                                    "S_TOKEN": "0x4b62bFAff61AB3985798e5202D2d167F567D0BCD",
                                    "V_TOKEN": "0xA38fCa8c6Bf9BdA52E76EB78f08CaA3BE7c5A970",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xc929ad75B72593967DE83E7F7Cda0493458261D9",
                                    "logoURI": "https://app.aave.com/icons/tokens/1inch.svg",
                                    "symbol": "1INCH"
                                },
                                "FRAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x853d955aCEf822Db058eb8505911ED77F175b99e",
                                    "A_TOKEN": "0xd4e245848d6E1220DBE62e155d89fa327E43CB06",
                                    "S_TOKEN": "0x219640546c0DFDDCb9ab3bcdA89B324e0a376367",
                                    "V_TOKEN": "0x88B8358F5BC87c2D7E116cCA5b65A9eEb2c5EA3F",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x45D270263BBee500CF8adcf2AbC0aC227097b036",
                                    "STATA_TOKEN": "0xEE66abD4D0f9908A48E08AE354B0f425De3e237E",
                                    "logoURI": "https://app.aave.com/icons/tokens/frax.svg",
                                    "symbol": "FRAX"
                                },
                                "GHO": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x40D16FC0246aD3160Ccc09B8D0D3A2cD28aE6C2f",
                                    "A_TOKEN": "0x00907f9921424583e7ffBfEdf84F92B7B2Be4977",
                                    "S_TOKEN": "0x3f3DF7266dA30102344A813F1a3D07f5F041B5AC",
                                    "V_TOKEN": "0x786dBff3f1292ae8F92ea68Cf93c30b34B1ed04B",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xD110cac5d8682A3b045D5524a9903E031d70FCCd",
                                    "logoURI": "https://app.aave.com/icons/tokens/gho.svg",
                                    "symbol": "GHO"
                                },
                                "RPL": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD33526068D116cE69F19A9ee46F0bd304F21A51f",
                                    "A_TOKEN": "0xB76CF92076adBF1D9C39294FA8e7A67579FDe357",
                                    "S_TOKEN": "0x41e330fd8F7eA31E2e8F02cC0C9392D1403597B4",
                                    "V_TOKEN": "0x8988ECA19D502fd8b9CCd03fA3bD20a6f599bc2A",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x4E155eD98aFE9034b7A5962f6C84c86d869daA9d",
                                    "logoURI": "https://app.aave.com/icons/tokens/rpl.svg",
                                    "symbol": "RPL"
                                },
                                "sDAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x83F20F44975D03b1b09e64809B757c47f942BEeA",
                                    "A_TOKEN": "0x4C612E3B15b96Ff9A6faED838F8d07d479a8dD4c",
                                    "S_TOKEN": "0x48Bc45f084988bC01933EA93EeFfEBC0416534f6",
                                    "V_TOKEN": "0x8Db9D35e117d8b93C6Ca9b644b25BaD5d9908141",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x29081f7aB5a644716EfcDC10D5c926c5fEe9F72B",
                                    "logoURI": "https://app.aave.com/icons/tokens/sdai.svg",
                                    "symbol": "sDAI"
                                },
                                "STG": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xAf5191B0De278C7286d6C7CC6ab6BB8A73bA2Cd6",
                                    "A_TOKEN": "0x1bA9843bD4327c6c77011406dE5fA8749F7E3479",
                                    "S_TOKEN": "0xc3115D0660b93AeF10F298886ae22E3Dd477E482",
                                    "V_TOKEN": "0x655568bDd6168325EC7e58Bf39b21A856F906Dc2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x7A9f34a0Aa917D438e9b6E630067062B7F8f6f3d",
                                    "logoURI": "https://app.aave.com/icons/tokens/stg.svg",
                                    "symbol": "STG"
                                },
                                "KNC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xdeFA4e8a7bcBA345F687a2f1456F5Edd9CE97202",
                                    "A_TOKEN": "0x5b502e3796385E1e9755d7043B9C945C3aCCeC9C",
                                    "S_TOKEN": "0xdfEE0C9eA1309cB9611F33972E72a72166fcF548",
                                    "V_TOKEN": "0x253127Ffc04981cEA8932F406710661c2f2c3fD2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xf8fF43E991A81e6eC886a3D281A2C6cC19aE70Fc",
                                    "logoURI": "https://app.aave.com/icons/tokens/knc.svg",
                                    "symbol": "KNC"
                                },
                                "FXS": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x3432B6A60D23Ca0dFCa7761B7ab56459D9C964D0",
                                    "A_TOKEN": "0x82F9c5ad306BBa1AD0De49bB5FA6F01bf61085ef",
                                    "S_TOKEN": "0x61dFd349140C239d3B61fEe203Efc811b518a317",
                                    "V_TOKEN": "0x68e9f0aD4e6f8F5DB70F6923d4d6d5b225B83b16",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x6Ebc52C8C1089be9eB3945C4350B68B8E4C2233f",
                                    "logoURI": "https://app.aave.com/icons/tokens/fxs.svg",
                                    "symbol": "FXS"
                                },
                                "crvUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf939E0A03FB07F59A73314E73794Be0E57ac1b4E",
                                    "A_TOKEN": "0xb82fa9f31612989525992FCfBB09AB22Eff5c85A",
                                    "S_TOKEN": "0xb55C604075D79486b8A329c396Fc711Be54B5330",
                                    "V_TOKEN": "0x028f7886F3e937f8479efaD64f31B3fE1119857a",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x02AeE5b225366302339748951E1a924617b8814F",
                                    "STATA_TOKEN": "0x848107491E029AFDe0AC543779c7790382f15929",
                                    "logoURI": "https://app.aave.com/icons/tokens/crvusd.svg",
                                    "symbol": "crvUSD"
                                },
                                "PYUSD": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x6c3ea9036406852006290770BEdFcAbA0e23A0e8",
                                    "A_TOKEN": "0x0C0d01AbF3e6aDfcA0989eBbA9d6e85dD58EaB1E",
                                    "S_TOKEN": "0x5B393DB4c72B1Bd82CE2834F6485d61b137Bc7aC",
                                    "V_TOKEN": "0x57B67e4DE077085Fd0AF2174e9c14871BE664546",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x150bAe7Ce224555D39AfdBc6Cb4B8204E594E022",
                                    "STATA_TOKEN": "0x00F2a835758B33f3aC53516Ebd69f3dc77B0D152",
                                    "logoURI": "https://app.aave.com/icons/tokens/pyusd.svg",
                                    "symbol": "PYUSD"
                                },
                                "weETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xCd5fE23C85820F7B72D0926FC9b05b43E359b7ee",
                                    "A_TOKEN": "0xBdfa7b7893081B35Fb54027489e2Bc7A38275129",
                                    "S_TOKEN": "0xBad6eF8e76E26F39e985474aD0974FDcabF85d37",
                                    "V_TOKEN": "0x77ad9BF13a52517AD698D65913e8D381300c8Bf3",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xf112aF6F0A332B815fbEf3Ff932c057E570b62d3",
                                    "logoURI": "https://app.aave.com/icons/tokens/weeth.svg",
                                    "symbol": "weETH"
                                },
                                "osETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf1C9acDc66974dFB6dEcB12aA385b9cD01190E38",
                                    "A_TOKEN": "0x927709711794F3De5DdBF1D176bEE2D55Ba13c21",
                                    "S_TOKEN": "0x48Fa27f511F40d16f9E7C913e9388d52d95bC6d2",
                                    "V_TOKEN": "0x8838eefF2af391863E1Bb8b1dF563F86743a8470",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x0A2AF898cEc35197e6944D9E0F525C2626393442",
                                    "logoURI": "https://app.aave.com/icons/tokens/oseth.svg",
                                    "symbol": "osETH"
                                },
                                "USDe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4c9EDD5852cd905f086C759E8383e09bff1E68B3",
                                    "A_TOKEN": "0x4F5923Fc5FD4a93352581b38B7cD26943012DECF",
                                    "S_TOKEN": "0x43Cc8AD0c223b38D9c04802bB184A2D97e497D38",
                                    "V_TOKEN": "0x015396E1F286289aE23a762088E863b3ec465145",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x55B6C4D3E8A27b8A1F5a263321b602e0fdEEcC17",
                                    "logoURI": "https://app.aave.com/icons/tokens/usde.svg",
                                    "symbol": "USDe"
                                },
                                "ETHx": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xA35b1B31Ce002FBF2058D22F30f95D405200A15b",
                                    "A_TOKEN": "0x1c0E06a0b1A4c160c17545FF2A951bfcA57C0002",
                                    "S_TOKEN": "0xBDfa7DE5CF7a7DdE4F023Cac842BF520fcF5395C",
                                    "V_TOKEN": "0x08a8Dc81AeA67F84745623aC6c72CDA3967aab8b",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xD6270dAabFe4862306190298C2B48fed9e15C847",
                                    "logoURI": "https://app.aave.com/icons/tokens/ethx.svg",
                                    "symbol": "ETHx"
                                },
                                "sUSDe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9D39A5DE30e57443BfF2A8307A4256c8797A3497",
                                    "A_TOKEN": "0x4579a27aF00A62C0EB156349f31B345c08386419",
                                    "S_TOKEN": "0xc9335dE638f4C96a8330b2FFc44353Bab58774e3",
                                    "V_TOKEN": "0xeFFDE9BFA8EC77c14C364055a200746d6e12BeD6",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xb37aE8aBa6C0C1Bf2c509fc06E11aa4AF29B665A",
                                    "logoURI": "https://app.aave.com/icons/tokens/susde.svg",
                                    "symbol": "sUSDe"
                                }
                            }
                        },
                        "10": {
                            "address": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xDA10009cBd5D07dd0CeCc66161FC93D7c9000da1",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x1a96fe91278bcF6F19665F642FE7a88cD5c360bb",
                                    "STATA_TOKEN": "0x6dDc64289bE8a71A707fB057d5d07Cc756055d6e",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x350a791Bfc2C21F9Ed5d10980Dad2e2638ffa7f6",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xCc232dcFAAE6354cE191Bd574108c1aD03f86450",
                                    "STATA_TOKEN": "0x39BCf217ACc4Bf2fCaF7BC8800E69D986912c75e",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x7F5c764cBc14f9669B88837ca1490cCa17c31607",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x2daA7078f78485A708003989cBc9a643e3b4B61f",
                                    "STATA_TOKEN": "0x9F281eb58fd98ad98EDe0fc4C553AD4D73e7Ca2C",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC.e"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x68f180fcCe6836688e9084f035309E29Bf0A2095",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xD702DD976Fb76Fffc2D3963D037dfDae5b04E593",
                                    "STATA_TOKEN": "0x6d998FeEFC7B3664eaD09CAf02b5a0fc2E365F18",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4200000000000000000000000000000000000006",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x13e3Ee699D1909E989722E753853AE30b17e08c5",
                                    "STATA_TOKEN": "0x98d69620C31869fD4822ceb6ADAB31180475FD37",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x94b008aA00579c1307B0EF2c499aD98a8ce58e58",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x70E6DBBFFc9c3c6fB4a9c349E3101B7dCEE67f4D",
                                    "STATA_TOKEN": "0x035c93db04E5aAea54E6cd0261C492a3e0638b37",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x76FB31fb4af56892A25e32cFC43De717950c9278",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x338ed6787f463394D24813b297401B9F05a8C9d1",
                                    "STATA_TOKEN": "0xae0Ca1B1Bc6cac26981B5e2b9c40f8Ce8A9082eE",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "sUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x8c6f28f2F1A3C87F0f938b96d27520d9751ec8d9",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xC77E9CF9603F5ef5503213229ABB1Fec3001f312",
                                    "STATA_TOKEN": "0x3A956E2Fcc7e71Ea14b0257d40BEbdB287d19652",
                                    "logoURI": "https://app.aave.com/icons/tokens/susd.svg",
                                    "symbol": "sUSD"
                                },
                                "OP": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4200000000000000000000000000000000000042",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x0D276FC14719f9292D5C1eA2198673d1f4269246",
                                    "STATA_TOKEN": "0xd4F1Cf9A038269FE8F03745C2875591Ad6438ab1",
                                    "logoURI": "https://app.aave.com/icons/tokens/op.svg",
                                    "symbol": "OP"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x1F32b1c2345538c0c6f582fCB022739c4A194Ebb",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x724E47194d97263ccb71FDad84b4fed18a8be387",
                                    "STATA_TOKEN": "0xb972abef80046A57409e37a7DF5dEf2638917516",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "LUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xc40F949F8a4e094D1b49a23ea9241D289B7b2819",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x8f4dAFb6Feb190e7846eb7665fD49FFb1177Ff8e",
                                    "STATA_TOKEN": "0x84648dc3Cefb601bc28a49A07a1A8Bad04D30Ad3",
                                    "logoURI": "https://app.aave.com/icons/tokens/lusd.svg",
                                    "symbol": "LUSD"
                                },
                                "MAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xdFA46478F9e5EA86d57387849598dbFB2e964b02",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xc6ac65E8f4F50a6655Efd78A92b6c503B5B625C8",
                                    "STATA_TOKEN": "0x60495bC8D8Baf7E866888ecC00491e37B47dfF24",
                                    "logoURI": "https://app.aave.com/icons/tokens/mai.svg",
                                    "symbol": "MAI"
                                },
                                "rETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9Bcef72be871e61ED4fBbc7630889beE758eb81D",
                                    "A_TOKEN": "0x724dc807b04555b71ed48a6896b6F41593b8C637",
                                    "S_TOKEN": "0xDC1fad70953Bb3918592b6fCc374fe05F5811B6a",
                                    "V_TOKEN": "0xf611aEb5013fD2c0511c9CD55c7dc5C1140741A6",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xF17e75D58D4Be71B8e674fA104B71a827e38F087",
                                    "STATA_TOKEN": "0xf9ce3c97b4b54F3D16861420f4816D9f68190B7B",
                                    "logoURI": "https://app.aave.com/icons/tokens/reth.svg",
                                    "symbol": "rETH"
                                },
                                "USDCn": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x0b2C639c533813f4Aa9D7837CAf62653d097Ff85",
                                    "A_TOKEN": "0x38d693cE1dF5AaDF7bC62595A37D667aD57922e5",
                                    "S_TOKEN": "0x8a9FdE6925a839F6B1932d16B36aC026F8d3FbdB",
                                    "V_TOKEN": "0x5D557B07776D12967914379C71a1310e917C7555",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x2daA7078f78485A708003989cBc9a643e3b4B61f",
                                    "STATA_TOKEN": "0x4DD03dfD36548C840B563745e3FBeC320F37BA7e",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                }
                            }
                        },
                        "137": {
                            "address": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x8f3Cf7ad23Cd3CaDbD9735AFf958023239c6A063",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xF86577E7d27Ed35b85A7645c58bAaA64453fe32B",
                                    "STATA_TOKEN": "0x83c59636e602787A6EEbBdA2915217B416193FcB",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x53E0bca35eC356BD5ddDFebbD1Fc0fD03FaBad39",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xd9FFdb71EbE7496cC440152d43986Aae0AB76665",
                                    "STATA_TOKEN": "0x37868a45c6741616F9E5a189dC0481AD70056B6a",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x2791Bca1f2de4661ED88A30C99A7a9449Aa84174",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x17E33D122FC34c7ad8FBd4a1995Dff9c8aE675eb",
                                    "STATA_TOKEN": "0x1017F4a86Fc3A3c824346d0b8C5e96A5029bDAf9",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC.e"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x1BFD67037B42Cf73acF2047067bd4F2C47D9BfD6",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xc907E116054Ad103354f2D350FD2514433D57F6f",
                                    "STATA_TOKEN": "0xbC0f50CCB8514Aa7dFEB297521c4BdEBc9C7d22d",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7ceB23fD6bC0adD59E62ac25578270cFf1b9f619",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xF9680D99D6C9589e2a93a78A04A279e509205945",
                                    "STATA_TOKEN": "0xb3D5Af0A52a35692D3FcbE37669b3B8C31dddE7D",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xc2132D05D31c914a87C6611C10748AEb04B58e8F",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xaA574f4f6E124E77a7a1B5Ed91c8b407000A7730",
                                    "STATA_TOKEN": "0x87A1fdc4C726c459f597282be639a045062c0E46",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD6DF932A45C0f255f85145f286eA0b292B21C90B",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x72484B12719E23115761D5DA1646945632979bB6",
                                    "STATA_TOKEN": "0xCA2E1E33E5BCF4978E2d683656E1f5610f8C4A7E",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "WMATIC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x0d500B1d8E8eF31E21C99d1Db9A6444d3ADf1270",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xAB594600376Ec9fD91F8e885dADF0CE036862dE0",
                                    "STATA_TOKEN": "0x98254592408E389D1dd2dBa318656C2C5c305b4E",
                                    "logoURI": "https://app.aave.com/icons/tokens/wmatic.svg",
                                    "symbol": "WMATIC"
                                },
                                "CRV": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x172370d5Cd63279eFa6d502DAB29171933a610AF",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x336584C8E6Dc19637A5b36206B1c79923111b405",
                                    "STATA_TOKEN": "0x4356941463eD4d75381AC23C9EF799B5d7C52AD8",
                                    "logoURI": "https://app.aave.com/icons/tokens/crv.svg",
                                    "symbol": "CRV"
                                },
                                "SUSHI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x0b3F868E0BE5597D5DB7fEB59E1CADBb0fdDa50a",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x49B0c695039243BBfEb8EcD054EB70061fd54aa0",
                                    "STATA_TOKEN": "0xe3eDe71d32240b7EC355F0e5DD1131BBe029F934",
                                    "logoURI": "https://app.aave.com/icons/tokens/sushi.svg",
                                    "symbol": "SUSHI"
                                },
                                "GHST": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x385Eeac5cB85A38A9a07A70c73e0a3271CfB54A7",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xDD229Ce42f11D8Ee7fFf29bDB71C7b81352e11be",
                                    "STATA_TOKEN": "0x123319636A6a9c85D9959399304F4cB23F64327e",
                                    "logoURI": "https://app.aave.com/icons/tokens/ghst.svg",
                                    "symbol": "GHST"
                                },
                                "BAL": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9a71012B13CA4d3D0Cdc72A177DF3ef03b0E76A3",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xD106B538F2A868c28Ca1Ec7E298C3325E0251d66",
                                    "STATA_TOKEN": "0x1a8969FD39AbaF228e690B172C4C3Eb7c67F95E1",
                                    "logoURI": "https://app.aave.com/icons/tokens/bal.svg",
                                    "symbol": "BAL"
                                },
                                "DPI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x85955046DF4668e1DD369D2DE9f3AEB98DD2A369",
                                    "A_TOKEN": "0x724dc807b04555b71ed48a6896b6F41593b8C637",
                                    "S_TOKEN": "0xDC1fad70953Bb3918592b6fCc374fe05F5811B6a",
                                    "V_TOKEN": "0xf611aEb5013fD2c0511c9CD55c7dc5C1140741A6",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x2e48b7924FBe04d575BA229A59b64547d9da16e9",
                                    "STATA_TOKEN": "0x73B788ACA5f4F0EeB3c6Da453cDf31041a77b36D",
                                    "logoURI": "https://app.aave.com/icons/tokens/dpi.svg",
                                    "symbol": "DPI"
                                },
                                "EURS": {
                                    "decimals": 2,
                                    "UNDERLYING": "0xE111178A87A3BFf0c8d18DECBa5798827539Ae99",
                                    "A_TOKEN": "0x38d693cE1dF5AaDF7bC62595A37D667aD57922e5",
                                    "S_TOKEN": "0x8a9FdE6925a839F6B1932d16B36aC026F8d3FbdB",
                                    "V_TOKEN": "0x5D557B07776D12967914379C71a1310e917C7555",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x73366Fe0AA0Ded304479862808e02506FE556a98",
                                    "STATA_TOKEN": "0x02E26888Ed3240BB38f26A2adF96Af9B52b167ea",
                                    "logoURI": "https://app.aave.com/icons/tokens/eurs.svg",
                                    "symbol": "EURS"
                                },
                                "jEUR": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4e3Decbb3645551B8A19f0eA1678079FCB33fB4c",
                                    "A_TOKEN": "0x6533afac2E7BCCB20dca161449A13A32D391fb00",
                                    "S_TOKEN": "0x6B4b37618D85Db2a7b469983C888040F7F05Ea3D",
                                    "V_TOKEN": "0x44705f578135cC5d703b4c9c122528C73Eb87145",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x73366Fe0AA0Ded304479862808e02506FE556a98",
                                    "STATA_TOKEN": "0xD992DaC78Ef3F34614E6a7d325b7b6A320FC0AB5",
                                    "logoURI": "https://app.aave.com/icons/tokens/jeur.svg",
                                    "symbol": "jEUR"
                                },
                                "EURA": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xE0B52e49357Fd4DAf2c15e02058DCE6BC0057db4",
                                    "A_TOKEN": "0x8437d7C167dFB82ED4Cb79CD44B7a32A1dd95c77",
                                    "S_TOKEN": "0x40B4BAEcc69B882e8804f9286b12228C27F8c9BF",
                                    "V_TOKEN": "0x3ca5FA07689F266e907439aFd1fBB59c44fe12f6",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x73366Fe0AA0Ded304479862808e02506FE556a98",
                                    "STATA_TOKEN": "0xd3eb8796Ed36f58E03B7b4b5AD417FA74931d2c4",
                                    "logoURI": "https://app.aave.com/icons/tokens/eura.svg",
                                    "symbol": "EURA"
                                },
                                "miMATIC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xa3Fa99A148fA48D14Ed51d610c367C61876997F1",
                                    "A_TOKEN": "0xeBe517846d0F36eCEd99C735cbF6131e1fEB775D",
                                    "S_TOKEN": "0x687871030477bf974725232F764aa04318A8b9c8",
                                    "V_TOKEN": "0x18248226C16BF76c032817854E7C83a2113B4f06",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x4ae2Ab1af7e3b0092dbF3A4B20ec3de8fC834873",
                                    "STATA_TOKEN": "0x8486B49433cCed038b51d18Ae3772CDB7E31CA5e",
                                    "logoURI": "https://app.aave.com/icons/tokens/mimatic.svg",
                                    "symbol": "miMATIC"
                                },
                                "stMATIC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x3A58a54C066FdC0f2D55FC9C89F0415C92eBf3C4",
                                    "A_TOKEN": "0xEA1132120ddcDDA2F119e99Fa7A27a0d036F7Ac9",
                                    "S_TOKEN": "0x1fFD28689DA7d0148ff0fCB669e9f9f0Fc13a219",
                                    "V_TOKEN": "0x6b030Ff3FB9956B1B69f475B77aE0d3Cf2CC5aFa",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x6D02E35031C4D99ee3A6A2BA47FaD0cFE355cA8f",
                                    "STATA_TOKEN": "0x867A180B7060fDC27610dC9096E93534F638A315",
                                    "logoURI": "https://app.aave.com/icons/tokens/stmatic.svg",
                                    "symbol": "stMATIC"
                                },
                                "MaticX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xfa68FB4628DFF1028CFEc22b4162FCcd0d45efb6",
                                    "A_TOKEN": "0x80cA0d8C38d2e2BcbaB66aA1648Bd1C7160500FE",
                                    "S_TOKEN": "0x62fC96b27a510cF4977B59FF952Dc32378Cc221d",
                                    "V_TOKEN": "0xB5b46F918C2923fC7f26DB76e8a6A6e9C4347Cf9",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xB0A72A5e454890e9715e059e8df8582a6B383DE3",
                                    "STATA_TOKEN": "0xbcDd5709641Af4BE99b1470A2B3A5203539132Ec",
                                    "logoURI": "https://app.aave.com/icons/tokens/maticx.svg",
                                    "symbol": "MaticX"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x03b54A6e9a984069379fae1a4fC4dBAE93B3bCCD",
                                    "A_TOKEN": "0xf59036CAEBeA7dC4b86638DFA2E3C97dA9FcCd40",
                                    "S_TOKEN": "0x173e54325AE58B072985DbF232436961981EA000",
                                    "V_TOKEN": "0x77fA66882a8854d883101Fb8501BD3CaD347Fc32",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xBD96b5ABBC6048c28184b462167E487533F2e35E",
                                    "STATA_TOKEN": "0x5274453F4CD5dD7280011a1Cca3B9e1b78EC59A6",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "USDCn": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x3c499c542cEF5E3811e1192ce70d8cC03d5c3359",
                                    "A_TOKEN": "0xA4D94019934D8333Ef880ABFFbF2FDd611C762BD",
                                    "S_TOKEN": "0xc889e9f8370D14A428a9857205d99BFdB400b757",
                                    "V_TOKEN": "0xE701126012EC0290822eEA17B794454d1AF8b030",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x17E33D122FC34c7ad8FBd4a1995Dff9c8aE675eb",
                                    "STATA_TOKEN": "0x2dCa80061632f3F87c9cA28364d1d0c30cD79a19",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                }
                            }
                        },
                        "534352": {
                            "address": "0x11fCfe756c05AD438e312a7fd934381537D3cFfe",
                            "ASSETS": {
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5300000000000000000000000000000000000004",
                                    "A_TOKEN": "0xf301805bE1Df81102C957f6d4Ce29d2B8c056B2a",
                                    "S_TOKEN": "0x117d9cF336287F46DBE509a43925cFF115Aa563c",
                                    "V_TOKEN": "0xfD7344CeB1Df9Cf238EcD667f4A6F99c6Ef44a56",
                                    "INTEREST_RATE_STRATEGY": "0xEC93d0BBA1b1e635ba0Fff4786dB323db49D99F0",
                                    "ORACLE": "0x6bF14CB0A831078629D993FDeBcB182b21A8774C",
                                    "STATA_TOKEN": "0x6b9DfaC194fa78a1882680E2cE19194D006AeEfd",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x06eFdBFf2a14a7c8E15944D1F4A48F9F95F663A4",
                                    "A_TOKEN": "0x1D738a3436A8C49CefFbaB7fbF04B660fb528CbD",
                                    "S_TOKEN": "0x59F359aA263f7Ac09876E869AF1F75b558904ed4",
                                    "V_TOKEN": "0x3d2E209af5BFa79297C88D6b57F89d792F6E28EE",
                                    "INTEREST_RATE_STRATEGY": "0xEC93d0BBA1b1e635ba0Fff4786dB323db49D99F0",
                                    "ORACLE": "0x427Fd98dbD1DbC2D4e792350caBe7c9665F35bee",
                                    "STATA_TOKEN": "0x9fA123bC7E6b61cC8a9D893673a4C6E5392FF4A7",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf610A9dfB7C89644979b4A0f27063E9e7d7Cda32",
                                    "A_TOKEN": "0x5B1322eeb46240b02e20062b8F0F9908d525B09c",
                                    "S_TOKEN": "0x18e3f125ce85e8D65AD2bb4f6b5fff110772A078",
                                    "V_TOKEN": "0x8a035644322129800C3f747f54Db0F4d3c0A2877",
                                    "INTEREST_RATE_STRATEGY": "0xEC93d0BBA1b1e635ba0Fff4786dB323db49D99F0",
                                    "ORACLE": "0x4EdAbf45e78363b8Dcd763bBbd05665c6e24975C",
                                    "STATA_TOKEN": "0x6e368c4dBf083e18a29aE63FC06AF9deDb3242F0",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                }
                            }
                        }
                    }
                    }//if the token is ERC20 token use this contract list and function
                    }
                },
        ```

    - LENDING_BORROW

        **Description:** Borrow assets from lending protocols using deposited collateral, with configurable borrowing parameters including interest rates, loan-to-value ratios, liquidation thresholds, and borrowing terms with real-time position health monitoring

        **Keywords:** borrow tokens, take loan, borrow crypto, lending borrow, get loan, borrow assets, take crypto loan, borrow cryptocurrency, lending loan, get defi loan, borrow from pool, take out loan, borrow against collateral, get borrowed, lending borrow assets, take token loan, borrow from protocol, get crypto borrowed, lending take loan, protocol borrowing

        ```tsx
        {
                    "action": "LENDING_BORROW",
                    "network": "1",
                    "inputs": [
                        {
                            "name": "asset",
                            "type": "string",
                            "default": ""
                        },
                        {
                            "name": "amount",
                            "type": "string",
                            "default": ""
                        }
                    ],
                    "outputs": [
                        {
                            "name": "success",
                            "type": "boolean"
                        }
                    ],
                    "protocol": {
                "name": "AAVE"
                    "borrowETH":{
                    "functionName": "borrowETH",
                    "contract": {
                        "42161": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0xecD4bd3121F9FD604ffaC631bF6d41ec12f1fafb"
                        },
                        "43114": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0x2DeC8BCE3471eD65B1bB558Fa28439D45bF446d0"
                        },
                        "8453": {
                            "pool": "0xA238Dd80C259a72e81d7e4664a9801593F98d1c5",
                            "address": "0x8be473dCfA93132658821E67CbEB684ec8Ea2E74"
                        },
                        "56": {
                            "pool": "0x6807dc923806fE8Fd134338EABCA509979a7e0cB",
                            "address": "0x326aB0868bD279382Be2DF5E228Cb8AF38649AB4"
                        },
                        "1": {
                            "pool": "0x87870Bca3F3fD6335C3F4ce8392D69350B4fA4E2",
                            "address": "0x893411580e590D62dDBca8a703d61Cc4A8c7b2b9"
                        },
                        "10": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0xe9E52021f4e11DEAD8661812A0A6c8627abA2a54"
                        },
                        "137": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0xC1E320966c485ebF2A0A2A6d3c0Dc860A156eB1B"
                        },
                        "534352": {
                            "pool": "0x11fCfe756c05AD438e312a7fd934381537D3cFfe",
                            "address": "0xFF75A4B698E3Ec95E608ac0f22A03B8368E05F5D"
                        }
                    }
                    }//if the token is native token use this contract list and function

                    "borrow": {
                    "functionName": "borrow",
                    "contract": {
                        "42161": {
                            "address": "0x794@a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xDA10009cBd5D07dd0CeCc66161FC93D7c9000da1",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x4a838a3Dac6633bB1fd932B6f356DecFCAf7803D",
                                    "STATA_TOKEN": "0xc91c5297d7E161aCC74b482aAfCc75B85cc0bfeD",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf97f4df75117a78c1A5a0DBb814Af92458539FB4",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x86E53CF1B870786351Da77A57575e79CB55812CB",
                                    "STATA_TOKEN": "0x27dE098EF2772386cBCf1a4c8BEb886368b7F9a9",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xDe25a88F87FEd9F8999fAbF6729dCB121893623C",
                                    "STATA_TOKEN": "0x0Bc9E52051f553E75550CA22C196bf132c52Cf0B",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC.e"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x2f2a2543B76A4166549F7aaB2e75Bef0aefC5B0f",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x6ce185860a4963106506C203335A2910413708e9",
                                    "STATA_TOKEN": "0x32B95Fbe04e5a51cF99FeeF4e57Cf7e3FC9c5A93",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x82aF49447D8a07e3bd95BD0d56f35241523fBab1",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x639Fe6ab55C921f74e7fac1ee960C0B6293ba612",
                                    "STATA_TOKEN": "0x352F3475716261dCC991Bd5F2aF973eB3D0F5878",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xFd086bC7CD5C481DCC9C85ebE478A1C0b69FCbb9",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x84dC1C52D7C340AA54B4e8799FBB31C3D28E67aD",
                                    "STATA_TOKEN": "0xb165a74407fE1e519d6bCbDeC1Ed3202B35a4140",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xba5DdD1f9d7F570dc94a51479a000E3BCE967196",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xaD1d5344AaDE45F43E596773Bcc4c423EAbdD034",
                                    "STATA_TOKEN": "0x1C0c8EcED17aE093b3C1a1a8fFeBE2E9513a9346",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "EURS": {
                                    "decimals": 2,
                                    "UNDERLYING": "0xD22a58f79e9481D1a88e00c343885A588b34b68B",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xA14d53bC1F1c0F31B4aA3BD109344E5009051a84",
                                    "STATA_TOKEN": "0x9a40747BE51185A416B181789B671E78a8d045dD",
                                    "logoURI": "https://app.aave.com/icons/tokens/eurs.svg",
                                    "symbol": "EURS"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5979D7b546E38E414F7E9822514be443A4800529",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x87fE1503beFBF98C35c7526B0c488d950F822C0F",
                                    "STATA_TOKEN": "0x7775d4Ae4Dbb79a624fB96AAcDB8Ca74F671c0DF",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "MAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x3F56e0c36d275367b8C502090EDF38289b3dEa0d",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x7a7cE08a1057723CCEDeA2462407427Ae33FFEb2",
                                    "STATA_TOKEN": "0xB4a0a2692D82301703B27082Cda45B083F68CAcE",
                                    "logoURI": "https://app.aave.com/icons/tokens/mai.svg",
                                    "symbol": "MAI"
                                },
                                "rETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xEC70Dcb4A1EFa46b8F2D97C310C9c4790ba5ffA8",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x256f33FC0110B1297f78f48524631D30B752480D",
                                    "STATA_TOKEN": "0x68235105d6d33A19369D24b746cb7481FB2b34fd",
                                    "logoURI": "https://app.aave.com/icons/tokens/reth.svg",
                                    "symbol": "rETH"
                                },
                                "LUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x93b346b6BC2548dA6A1E7d98E9a421B42541425b",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x341B110bDF665A20F0D5f84A92FcAF5EbeEBC629",
                                    "STATA_TOKEN": "0xDbB6314b5b07E63B7101844c0346309B79f8C20A",
                                    "logoURI": "https://app.aave.com/icons/tokens/lusd.svg",
                                    "symbol": "LUSD"
                                },
                                "USDCn": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xaf88d065e77c8cC2239327C5EDb3A432268e5831",
                                    "A_TOKEN": "0x724dc807b04555b71ed48a6896b6F41593b8C637",
                                    "S_TOKEN": "0xDC1fad70953Bb3918592b6fCc374fe05F5811B6a",
                                    "V_TOKEN": "0xf611aEb5013fD2c0511c9CD55c7dc5C1140741A6",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xDe25a88F87FEd9F8999fAbF6729dCB121893623C",
                                    "STATA_TOKEN": "0x7CFaDFD5645B50bE87d546f42699d863648251ad",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "FRAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x17FC002b466eEc40DaE837Fc4bE5c67993ddBd6F",
                                    "A_TOKEN": "0x38d693cE1dF5AaDF7bC62595A37D667aD57922e5",
                                    "S_TOKEN": "0x8a9FdE6925a839F6B1932d16B36aC026F8d3FbdB",
                                    "V_TOKEN": "0x5D557B07776D12967914379C71a1310e917C7555",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x06919EB75Bd6BA817D38CC70C1CA588ac7a01C10",
                                    "STATA_TOKEN": "0x89AEc2023f89E26Dbb7eaa7a98fe3996f9d112A8",
                                    "logoURI": "https://app.aave.com/icons/tokens/frax.svg",
                                    "symbol": "FRAX"
                                },
                                "ARB": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x912CE59144191C1204E64559FE8253a0e49E6548",
                                    "A_TOKEN": "0x6533afac2E7BCCB20dca161449A13A32D391fb00",
                                    "S_TOKEN": "0x6B4b37618D85Db2a7b469983C888040F7F05Ea3D",
                                    "V_TOKEN": "0x44705f578135cC5d703b4c9c122528C73Eb87145",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xb2A824043730FE05F3DA2efaFa1CBbe83fa548D6",
                                    "STATA_TOKEN": "0x9b5637d7952BC9fa2D693aAE51f3103760Bf2693",
                                    "logoURI": "https://app.aave.com/icons/tokens/arb.svg",
                                    "symbol": "ARB"
                                },
                                "weETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x35751007a407ca6FEFfE80b3cB397736D2cf4dbe",
                                    "A_TOKEN": "0x8437d7C167dFB82ED4Cb79CD44B7a32A1dd95c77",
                                    "S_TOKEN": "0x40B4BAEcc69B882e8804f9286b12228C27F8c9BF",
                                    "V_TOKEN": "0x3ca5FA07689F266e907439aFd1fBB59c44fe12f6",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x517276B5972C4Db7E88B9F76Ee500E888a2D73C3",
                                    "logoURI": "https://app.aave.com/icons/tokens/weeth.svg",
                                    "symbol": "weETH"
                                },
                                "GHO": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7dfF72693f6A4149b17e7C6314655f6A9F7c8B33",
                                    "A_TOKEN": "0xeBe517846d0F36eCEd99C735cbF6131e1fEB775D",
                                    "S_TOKEN": "0x687871030477bf974725232F764aa04318A8b9c8",
                                    "V_TOKEN": "0x18248226C16BF76c032817854E7C83a2113B4f06",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xB05984aD83C20b3ADE7bf97a9a0Cb539DDE28DBb",
                                    "logoURI": "https://app.aave.com/icons/tokens/gho.svg",
                                    "symbol": "GHO"
                                }
                            }
                        },
                        "43114": {
                            "address": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAIe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xd586E7F844cEa2F87f50152665BCbc2C279D8d70",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xf82da795727633aFA9BB0f1B08A87c0F6A38723f",
                                    "STATA_TOKEN": "0x02F3f6c8A432C1e49f3359d7d36887C25d8A5888",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI.e"
                                },
                                "LINKe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5947BB275c521040051D82396192181b413227A3",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x49ccd9ca821EfEab2b98c60dC60F518E765EDe9a",
                                    "STATA_TOKEN": "0x8B773Ab77Dff01985D438961dBCE58382a70cA52",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK.e"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xB97EF9Ef8734C71904D8002F8b6Bc66Dd9c48a6E",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xD8277249e871BE9A402fa286C2C5ec16046dC512",
                                    "STATA_TOKEN": "0xC509aB7bB4eDbF193b82264D499a7Fc526Cd01F4",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "WBTCe": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x50b7545627a5162F82A992c33b87aDc75187B218",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x2779D32d5166BAaa2B2b658333bA7e6Ec0C65743",
                                    "STATA_TOKEN": "0xE3C0f42EAF1a4BFe37CbA105e5463564BA7730aE",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC.e"
                                },
                                "WETHe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x49D5c2BdFfac6CE2BFdB6640F4F80f226bc10bAB",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x976B3D034E162d8bD72D6b9C989d545b839003b0",
                                    "STATA_TOKEN": "0xf8E24175D01653fd6AA203C2C17B1e4Dd1CA2731",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH.e"
                                },
                                "USDt": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x9702230A8Ea53601f5cD2dc00fDBc13d4dF4A8c7",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x39185f2236A6022b682e8BB93C040d125DA093CF",
                                    "STATA_TOKEN": "0x5525Ee69BC1e354B356864187De486fab5AD67d7",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDt"
                                },
                                "AAVEe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x63a72806098Bd3D9520cC43356dD78afe5D386D9",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x3CA13391E9fb38a75330fb28f8cc2eB3D9ceceED",
                                    "STATA_TOKEN": "0xac0746AfD13DEbe2a43a6c8745Fb83Fd2A2909cA",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE.e"
                                },
                                "WAVAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xB31f66AA3C1e785363F0875A1B74E27b85FD66c7",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x0A77230d17318075983913bC2145DB16C7366156",
                                    "STATA_TOKEN": "0x6A02C7a974F1F13A67980C80F774eC1d2eD8f98d",
                                    "logoURI": "https://app.aave.com/icons/tokens/wavax.svg",
                                    "symbol": "WAVAX"
                                },
                                "sAVAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x2b2C81e08f1Af8835a78Bb2A90AE924ACE0eA4bE",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xB2B332f27e4B7305649a228C31Ed9858c5a6bAD9",
                                    "STATA_TOKEN": "0x4F059cA8a2a5BF8895Ee731f2E901cCB769FB95f",
                                    "logoURI": "https://app.aave.com/icons/tokens/savax.svg",
                                    "symbol": "sAVAX"
                                },
                                "FRAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD24C2Ad096400B6FBcd2ad8B24E7acBc21A1da64",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x6208576378D06ce69A27987b7A524A9B15d499a4",
                                    "STATA_TOKEN": "0xA3c2ffE702F4cD265B2249AB5f84Fab81FFf6c73",
                                    "logoURI": "https://app.aave.com/icons/tokens/frax.svg",
                                    "symbol": "FRAX"
                                },
                                "MAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5c49b268c9841AFF1Cc3B0a418ff5c3442eE3F3b",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xCcC55Db26B78a19Dba1beE0066F9c1665575439A",
                                    "STATA_TOKEN": "0x08cC59E51BB0Bc322B4D251f7262dB864d6150ce",
                                    "logoURI": "https://app.aave.com/icons/tokens/mai.svg",
                                    "symbol": "MAI"
                                },
                                "BTCb": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x152b9d0FdC40C096757F570A51E494bd4b943E50",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x2779D32d5166BAaa2B2b658333bA7e6Ec0C65743",
                                    "STATA_TOKEN": "0x34d768cc830c32DcD743321c09A2A702651bF9a2",
                                    "logoURI": "https://app.aave.com/icons/tokens/btc.svg",
                                    "symbol": "BTC.b"
                                }
                            }
                        },
                        "8453": {
                            "address": "0xA238Dd80C259a72e81d7e4664a9801593F98d1c5",
                            "ASSETS": {
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4200000000000000000000000000000000000006",
                                    "A_TOKEN": "0xD4a0e0b9149BCee3C920d2E00b5dE09138fd8bb7",
                                    "S_TOKEN": "0xaED3b56FeA82E809665f02AcBcDEc0816c75f4d9",
                                    "V_TOKEN": "0x24e6e0795b3c7c71D965fCc4f371803d1c1DcA1E",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x71041dddad3595F9CEd3DcCFBe3D1F4b0a16Bb70",
                                    "STATA_TOKEN": "0x468973e3264F2aEba0417A8f2cD0Ec397E738898",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "cbETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x2Ae3F1Ec7F1F5012CFEab0185bfc7aa3cf0DEc22",
                                    "A_TOKEN": "0xcf3D55c10DB69f28fD1A75Bd73f3D8A2d9c595ad",
                                    "S_TOKEN": "0xa9dF5c62d16d3f496673F4d736852017b086eCA0",
                                    "V_TOKEN": "0x1DabC36f19909425f654777249815c073E8Fd79F",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x8e11Ad4531826ff47BD8157a2c705F5422Da6A61",
                                    "STATA_TOKEN": "0x16A004065dfb11276DcB29Dc03fb8A85f9A43C6e",
                                    "logoURI": "https://app.aave.com/icons/tokens/cbeth.svg",
                                    "symbol": "cbETH"
                                },
                                "USDbC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xd9aAEc86B65D86f6A7B5B1b0c42FFA531710b6CA",
                                    "A_TOKEN": "0x0a1d576f3eFeF75b330424287a95A366e8281D54",
                                    "S_TOKEN": "0xBBaDd47fbaFa9dE717FE203e4707DEB893C64654",
                                    "V_TOKEN": "0x7376b2F323dC56fCd4C191B34163ac8a84702DAB",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x978D8878b53Fbe40dab7D4AB47b97AB622FFeF9f",
                                    "STATA_TOKEN": "0x6fCe2756794128B1771324caA860965801DCbCdB",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdbc.svg",
                                    "symbol": "USDbC"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xc1CBa3fCea344f92D9239c08C0568f6F2F0ee452",
                                    "A_TOKEN": "0x99CBC45ea5bb7eF3a5BC08FB1B7E56bB2442Ef0D",
                                    "S_TOKEN": "0xfe742Fa2a84294E8316F05b17c05090Fc68B5105",
                                    "V_TOKEN": "0x41A7C3f5904ad176dACbb1D99101F59ef0811DC1",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x56038D3998C42db18ba3B821bD1EbaB9B678e657",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913",
                                    "A_TOKEN": "0x4e65fE4DbA92790696d040ac24Aa414708F5c0AB",
                                    "S_TOKEN": "0x03506214379aA86ad1176af71c260278cfa10B38",
                                    "V_TOKEN": "0x59dca05b6c26dbd64b5381374aAaC5CD05644C28",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x978D8878b53Fbe40dab7D4AB47b97AB622FFeF9f",
                                    "STATA_TOKEN": "0x4EA71A20e655794051D1eE8b6e4A3269B13ccaCc",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "weETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x04C0599Ae5A44757c0af6F9eC3b93da8976c150A",
                                    "A_TOKEN": "0x7C307e128efA31F540F2E2d976C995E0B65F51F6",
                                    "S_TOKEN": "0xCBEdA45432D5325585ACAD29244f113C237B6Cf0",
                                    "V_TOKEN": "0x8D2e3F1f4b38AA9f1ceD22ac06019c7561B03901",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0xFc4d1d7a8FD1E6719e361e16044b460737F12C44",
                                    "logoURI": "https://app.aave.com/icons/tokens/weeth.svg",
                                    "symbol": "weETH"
                                }
                            }
                        },
                        "56": {
                            "address": "0x326aB0868bD279382Be2DF5E228Cb8AF38649AB4",
                            "ASSETS": {
                                "Cake": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82",
                                    "A_TOKEN": "0x4199CC1F5ed0d796563d7CcB2e036253E2C18281",
                                    "S_TOKEN": "0x57e95511de39890D3e782df4b19F0D97A05DF64A",
                                    "V_TOKEN": "0xE20dBC7119c635B1B51462f844861258770e0699",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0xB6064eD41d4f67e353768aA239cA86f4F73665a1",
                                    "STATA_TOKEN": "0x3854354CE3681da1D7F550073061E92a4a7d1B27",
                                    "logoURI": "https://app.aave.com/icons/tokens/cake.svg",
                                    "symbol": "Cake"
                                },
                                "WBNB": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xbb4CdB9CBd36B01bD1cBaEBF2De08d9173bc095c",
                                    "A_TOKEN": "0x9B00a09492a626678E5A3009982191586C444Df9",
                                    "S_TOKEN": "0x5cc46d2b1103aB23CFD63eF8631480bbf4eB40FE",
                                    "V_TOKEN": "0x0E76414d433ddfe8004d2A7505d218874875a996",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x0567F2323251f0Aab15c8dFb1967E4e8A7D42aeE",
                                    "STATA_TOKEN": "0x436baCb4C66583de4Cb16e13a1A0D9A3075DE425",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbnb.svg",
                                    "symbol": "WBNB"
                                },
                                "BTCB": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7130d2A12B9BCbFAe4f2634d864A1Ee1Ce3Ead9c",
                                    "A_TOKEN": "0x56a7ddc4e848EbF43845854205ad71D5D5F72d3D",
                                    "S_TOKEN": "0x9Ef6D76740713C674A6e4f38B863E62D10965053",
                                    "V_TOKEN": "0x7b1E82F4f542fbB25D64c5523Fe3e44aBe4F2702",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x264990fbd0A4796A3E3d8E37C4d5F87a3aCa5Ebf",
                                    "STATA_TOKEN": "0x1F66b530084079d35478A069d9c4424F9c9C320c",
                                    "logoURI": "https://app.aave.com/icons/tokens/btcb.svg",
                                    "symbol": "BTCB"
                                },
                                "ETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x2170Ed0880ac9A755fd29B2688956BD959F933F8",
                                    "A_TOKEN": "0x2E94171493fAbE316b6205f1585779C887771E2F",
                                    "S_TOKEN": "0xa8327EE1858E06983af6690d24e77774807109d4",
                                    "V_TOKEN": "0x8FDea7891b4D6dbdc746309245B316aF691A636C",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x9ef1B8c0E4F7dc8bF5719Ea496883DC6401d5b2e",
                                    "STATA_TOKEN": "0x52077433fB7053D747E2846aD0C18ff5015C368E",
                                    "logoURI": "https://app.aave.com/icons/tokens/eth.svg",
                                    "symbol": "ETH"
                                },
                                "USDC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x8AC76a51cc950d9822D68b83fE1Ad97B32Cd580d",
                                    "A_TOKEN": "0x00901a076785e0906d1028c7d6372d247bec7d61",
                                    "S_TOKEN": "0xCcC260D9778F900eAd566Fa2E1D622E667677653",
                                    "V_TOKEN": "0xcDBBEd5606d9c5C98eEedd67933991dC17F0c68d",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0xaFcFF74AE956f4c23c27Db49659D4a7F350415C1",
                                    "STATA_TOKEN": "0x3906cDdfb781f02B21f21BD81ed7Fd8DC37075E1",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "USDT": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x55d398326f99059fF775485246999027B3197955",
                                    "A_TOKEN": "0xa9251ca9DE909CB71783723713B21E4233fbf1B1",
                                    "S_TOKEN": "0xB735D922a36d4337f561CE433594727e1bc8bD01",
                                    "V_TOKEN": "0xF8bb2Be50647447Fb355e3a77b81be4db64107cd",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x0F682319Ed4A240b7a2599A48C965049515D9bC3",
                                    "STATA_TOKEN": "0x0471D185cc7Be61E154277cAB2396cD397663da6",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "FDUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xc5f0f7b66764F6ec8C8Dff7BA683102295E16409",
                                    "A_TOKEN": "0x75bd1A659bdC62e4C313950d44A2416faB43E785",
                                    "S_TOKEN": "0x5543d347bfae77A5FF913e589aB6D6ad520f1C73",
                                    "V_TOKEN": "0xE628B8a123e6037f1542e662B9F55141a16945C8",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x60a117Fa5bAbee4d645884fB11E413Da4F893b6D",
                                    "STATA_TOKEN": "0x4d074aAa0821073dA827f7bf6a02cF905b394ed0",
                                    "logoURI": "https://app.aave.com/icons/tokens/fdusd.svg",
                                    "symbol": "FDUSD"
                                }
                            }
                        },
                        "1": {
                            "address": "0x87870Bca3F3fD6335C3F4ce8392D69350B4fA4E2",
                            "ASSETS": {
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2",
                                    "A_TOKEN": "0x4d5F47FA6A74757f35C14fD3a6Ef8E3C9BC514E8",
                                    "S_TOKEN": "0x102633152313C81cD80419b6EcF66d14Ad68949A",
                                    "V_TOKEN": "0xeA51d7853EEFb32b6ee06b1C12E6dcCA88Be0fFE",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x5f4eC3Df9cbd43714FE2740f5E3616155c5b8419",
                                    "STATA_TOKEN": "0x252231882FB38481497f3C767469106297c8d93b",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7f39C581F595B53c5cb19bD0b3f8dA6c935E2Ca0",
                                    "A_TOKEN": "0x0B925eD163218f6662a35e0f0371Ac234f9E9371",
                                    "S_TOKEN": "0x39739943199c0fBFe9E5f1B5B160cd73a64CB85D",
                                    "V_TOKEN": "0xC96113eED8cAB59cD8A66813bCB0cEb29F06D2e4",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xB4aB0c94159bc2d8C133946E7241368fc2F2a010",
                                    "STATA_TOKEN": "0x322AA5F5Be95644d6c36544B6c5061F072D16DF5",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x2260FAC5E5542a773Aa44fBCfeDf7C193bc2C599",
                                    "A_TOKEN": "0x5Ee5bf7ae06D1Be5997A1A72006FE6C607eC6DE8",
                                    "S_TOKEN": "0xA1773F1ccF6DB192Ad8FE826D15fe1d328B03284",
                                    "V_TOKEN": "0x40aAbEf1aa8f0eEc637E0E7d92fbfFB2F26A8b7B",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x230E0321Cf38F09e247e50Afc7801EA2351fe56F",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48",
                                    "A_TOKEN": "0x98C23E9d8f34FEFb1B7BD6a91B7FF122F4e16F5c",
                                    "S_TOKEN": "0xB0fe3D292f4bd50De902Ba5bDF120Ad66E9d7a39",
                                    "V_TOKEN": "0x72E95b8931767C79bA4EeE721354d6E99a61D004",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x736bF902680e68989886e9807CD7Db4B3E015d3C",
                                    "STATA_TOKEN": "0x73edDFa87C71ADdC275c2b9890f5c3a8480bC9E6",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x6B175474E89094C44Da98b954EedeAC495271d0F",
                                    "A_TOKEN": "0x018008bfb33d285247A21d44E50697654f754e63",
                                    "S_TOKEN": "0x413AdaC9E2Ef8683ADf5DDAEce8f19613d60D1bb",
                                    "V_TOKEN": "0xcF8d0c70c850859266f5C338b38F9D663181C314",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xaEb897E1Dc6BbdceD3B9D551C71a8cf172F27AC4",
                                    "STATA_TOKEN": "0xaf270C38fF895EA3f95Ed488CEACe2386F038249",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x514910771AF9Ca656af840dff83E8264EcF986CA",
                                    "A_TOKEN": "0x5E8C8A7243651DB1384C0dDfDbE39761E8e7E51a",
                                    "S_TOKEN": "0x63B1129ca97D2b9F97f45670787Ac12a9dF1110a",
                                    "V_TOKEN": "0x4228F8895C7dDA20227F6a5c6751b8Ebf19a6ba8",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x2c1d072e956AFFC0D435Cb7AC38EF18d24d9127c",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7Fc66500c84A76Ad7e9c93437bFc5Ac33E2DDaE9",
                                    "A_TOKEN": "0xA700b4eB416Be35b2911fd5Dee80678ff64fF6C9",
                                    "S_TOKEN": "0x268497bF083388B1504270d0E717222d3A87D6F2",
                                    "V_TOKEN": "0xBae535520Abd9f8C85E58929e0006A2c8B372F74",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x547a514d5e3769680Ce22B2361c10Ea13619e8a9",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "cbETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xBe9895146f7AF43049ca1c1AE358B0541Ea49704",
                                    "A_TOKEN": "0x977b6fc5dE62598B08C85AC8Cf2b745874E8b78c",
                                    "S_TOKEN": "0x82bE6012cea6D147B968eBAea5ceEcF6A5b4F493",
                                    "V_TOKEN": "0x0c91bcA95b5FE69164cE583A2ec9429A569798Ed",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x6243d2F41b4ec944F731f647589E28d9745a2674",
                                    "logoURI": "https://app.aave.com/icons/tokens/cbeth.svg",
                                    "symbol": "cbETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xdAC17F958D2ee523a2206206994597C13D831ec7",
                                    "A_TOKEN": "0x23878914EFE38d27C4D67Ab83ed1b93A74D4086a",
                                    "S_TOKEN": "0x822Fa72Df1F229C3900f5AD6C3Fa2C424D691622",
                                    "V_TOKEN": "0x6df1C1E379bC5a00a7b4C6e67A203333772f45A8",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xC26D4a1c46d884cfF6dE9800B6aE7A8Cf48B4Ff8",
                                    "STATA_TOKEN": "0x862c57d48becB45583AEbA3f489696D22466Ca1b",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "rETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xae78736Cd615f374D3085123A210448E74Fc6393",
                                    "A_TOKEN": "0xCc9EE9483f662091a1de4795249E24aC0aC2630f",
                                    "S_TOKEN": "0x1d1906f909CAe494c7441604DAfDDDbD0485A925",
                                    "V_TOKEN": "0xae8593DD575FE29A9745056aA91C4b746eee62C8",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x5AE8365D0a30D67145f0c55A08760C250559dB64",
                                    "logoURI": "https://app.aave.com/icons/tokens/reth.svg",
                                    "symbol": "rETH"
                                },
                                "LUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5f98805A4E8be255a32880FDeC7F6728C6568bA0",
                                    "A_TOKEN": "0x3Fe6a295459FAe07DF8A0ceCC36F37160FE86AA9",
                                    "S_TOKEN": "0x37A6B708FDB1483C231961b9a7F145261E815fc3",
                                    "V_TOKEN": "0x33652e48e4B74D18520f11BfE58Edd2ED2cEc5A2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x9eCdfaCca946614cc32aF63F3DBe50959244F3af",
                                    "STATA_TOKEN": "0xDBf5E36569798D1E39eE9d7B1c61A7409a74F23A",
                                    "logoURI": "https://app.aave.com/icons/tokens/lusd.svg",
                                    "symbol": "LUSD"
                                },
                                "CRV": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD533a949740bb3306d119CC777fa900bA034cd52",
                                    "A_TOKEN": "0x7B95Ec873268a6BFC6427e7a28e396Db9D0ebc65",
                                    "S_TOKEN": "0x90D9CD005E553111EB8C9c31Abe9706a186b6048",
                                    "V_TOKEN": "0x1b7D3F4b3c032a5AE656e30eeA4e8E1Ba376068F",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xCd627aA160A6fA45Eb793D19Ef54f5062F20f33f",
                                    "logoURI": "https://app.aave.com/icons/tokens/crv.svg",
                                    "symbol": "CRV"
                                },
                                "MKR": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9f8F72aA9304c8B593d555F12eF6589cC3A579A2",
                                    "A_TOKEN": "0x8A458A9dc9048e005d22849F470891b840296619",
                                    "S_TOKEN": "0x0496372BE7e426D28E89DEBF01f19F014d5938bE",
                                    "V_TOKEN": "0x6Efc73E54E41b27d2134fF9f98F15550f30DF9B1",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xec1D1B3b0443256cc3860e24a46F108e699484Aa",
                                    "logoURI": "https://app.aave.com/icons/tokens/mkr.svg",
                                    "symbol": "MKR"
                                },
                                "SNX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xC011a73ee8576Fb46F5E1c5751cA3B9Fe0af2a6F",
                                    "A_TOKEN": "0xC7B4c17861357B8ABB91F25581E7263E08DCB59c",
                                    "S_TOKEN": "0x478E1ec1A2BeEd94c1407c951E4B9e22d53b2501",
                                    "V_TOKEN": "0x8d0de040e8aAd872eC3c33A3776dE9152D3c34ca",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xDC3EA94CD0AC27d9A86C180091e7f78C683d3699",
                                    "logoURI": "https://app.aave.com/icons/tokens/snx.svg",
                                    "symbol": "SNX"
                                },
                                "BAL": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xba100000625a3754423978a60c9317c58a424e3D",
                                    "A_TOKEN": "0x2516E7B3F76294e03C42AA4c5b5b4DCE9C436fB8",
                                    "S_TOKEN": "0xB368d45aaAa07ee2c6275Cb320D140b22dE43CDD",
                                    "V_TOKEN": "0x3D3efceb4Ff0966D34d9545D3A2fa2dcdBf451f2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xdF2917806E30300537aEB49A7663062F4d1F2b5F",
                                    "logoURI": "https://app.aave.com/icons/tokens/bal.svg",
                                    "symbol": "BAL"
                                },
                                "UNI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x1f9840a85d5aF5bf1D1762F925BDADdC4201F984",
                                    "A_TOKEN": "0xF6D2224916DDFbbab6e6bd0D1B7034f4Ae0CaB18",
                                    "S_TOKEN": "0x2FEc76324A0463c46f32e74A86D1cf94C02158DC",
                                    "V_TOKEN": "0xF64178Ebd2E2719F2B1233bCb5Ef6DB4bCc4d09a",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x553303d460EE0afB37EdFf9bE42922D8FF63220e",
                                    "logoURI": "https://app.aave.com/icons/tokens/uni.svg",
                                    "symbol": "UNI"
                                },
                                "LDO": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5A98FcBEA516Cf06857215779Fd812CA3beF1B32",
                                    "A_TOKEN": "0x9A44fd41566876A39655f74971a3A6eA0a17a454",
                                    "S_TOKEN": "0xa0a5bF5781Aeb548db9d4226363B9e89287C5FD2",
                                    "V_TOKEN": "0xc30808705C01289A3D306ca9CAB081Ba9114eC82",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xb01e6C9af83879B8e06a092f0DD94309c0D497E4",
                                    "logoURI": "https://app.aave.com/icons/tokens/ldo.svg",
                                    "symbol": "LDO"
                                },
                                "ENS": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xC18360217D8F7Ab5e7c516566761Ea12Ce7F9D72",
                                    "A_TOKEN": "0x545bD6c032eFdde65A377A6719DEF2796C8E0f2e",
                                    "S_TOKEN": "0x7617d02E311CdE347A0cb45BB7DF2926BBaf5347",
                                    "V_TOKEN": "0xd180D7fdD4092f07428eFE801E17BC03576b3192",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x5C00128d4d1c2F4f652C267d7bcdD7aC99C16E16",
                                    "logoURI": "https://app.aave.com/icons/tokens/ens.svg",
                                    "symbol": "ENS"
                                },
                                "ONE_INCH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x111111111117dC0aa78b770fA6A738034120C302",
                                    "A_TOKEN": "0x71Aef7b30728b9BB371578f36c5A1f1502a5723e",
                                    "S_TOKEN": "0x4b62bFAff61AB3985798e5202D2d167F567D0BCD",
                                    "V_TOKEN": "0xA38fCa8c6Bf9BdA52E76EB78f08CaA3BE7c5A970",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xc929ad75B72593967DE83E7F7Cda0493458261D9",
                                    "logoURI": "https://app.aave.com/icons/tokens/1inch.svg",
                                    "symbol": "1INCH"
                                },
                                "FRAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x853d955aCEf822Db058eb8505911ED77F175b99e",
                                    "A_TOKEN": "0xd4e245848d6E1220DBE62e155d89fa327E43CB06",
                                    "S_TOKEN": "0x219640546c0DFDDCb9ab3bcdA89B324e0a376367",
                                    "V_TOKEN": "0x88B8358F5BC87c2D7E116cCA5b65A9eEb2c5EA3F",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x45D270263BBee500CF8adcf2AbC0aC227097b036",
                                    "STATA_TOKEN": "0xEE66abD4D0f9908A48E08AE354B0f425De3e237E",
                                    "logoURI": "https://app.aave.com/icons/tokens/frax.svg",
                                    "symbol": "FRAX"
                                },
                                "GHO": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x40D16FC0246aD3160Ccc09B8D0D3A2cD28aE6C2f",
                                    "A_TOKEN": "0x00907f9921424583e7ffBfEdf84F92B7B2Be4977",
                                    "S_TOKEN": "0x3f3DF7266dA30102344A813F1a3D07f5F041B5AC",
                                    "V_TOKEN": "0x786dBff3f1292ae8F92ea68Cf93c30b34B1ed04B",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xD110cac5d8682A3b045D5524a9903E031d70FCCd",
                                    "logoURI": "https://app.aave.com/icons/tokens/gho.svg",
                                    "symbol": "GHO"
                                },
                                "RPL": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD33526068D116cE69F19A9ee46F0bd304F21A51f",
                                    "A_TOKEN": "0xB76CF92076adBF1D9C39294FA8e7A67579FDe357",
                                    "S_TOKEN": "0x41e330fd8F7eA31E2e8F02cC0C9392D1403597B4",
                                    "V_TOKEN": "0x8988ECA19D502fd8b9CCd03fA3bD20a6f599bc2A",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x4E155eD98aFE9034b7A5962f6C84c86d869daA9d",
                                    "logoURI": "https://app.aave.com/icons/tokens/rpl.svg",
                                    "symbol": "RPL"
                                },
                                "sDAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x83F20F44975D03b1b09e64809B757c47f942BEeA",
                                    "A_TOKEN": "0x4C612E3B15b96Ff9A6faED838F8d07d479a8dD4c",
                                    "S_TOKEN": "0x48Bc45f084988bC01933EA93EeFfEBC0416534f6",
                                    "V_TOKEN": "0x8Db9D35e117d8b93C6Ca9b644b25BaD5d9908141",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x29081f7aB5a644716EfcDC10D5c926c5fEe9F72B",
                                    "logoURI": "https://app.aave.com/icons/tokens/sdai.svg",
                                    "symbol": "sDAI"
                                },
                                "STG": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xAf5191B0De278C7286d6C7CC6ab6BB8A73bA2Cd6",
                                    "A_TOKEN": "0x1bA9843bD4327c6c77011406dE5fA8749F7E3479",
                                    "S_TOKEN": "0xc3115D0660b93AeF10F298886ae22E3Dd477E482",
                                    "V_TOKEN": "0x655568bDd6168325EC7e58Bf39b21A856F906Dc2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x7A9f34a0Aa917D438e9b6E630067062B7F8f6f3d",
                                    "logoURI": "https://app.aave.com/icons/tokens/stg.svg",
                                    "symbol": "STG"
                                },
                                "KNC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xdeFA4e8a7bcBA345F687a2f1456F5Edd9CE97202",
                                    "A_TOKEN": "0x5b502e3796385E1e9755d7043B9C945C3aCCeC9C",
                                    "S_TOKEN": "0xdfEE0C9eA1309cB9611F33972E72a72166fcF548",
                                    "V_TOKEN": "0x253127Ffc04981cEA8932F406710661c2f2c3fD2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xf8fF43E991A81e6eC886a3D281A2C6cC19aE70Fc",
                                    "logoURI": "https://app.aave.com/icons/tokens/knc.svg",
                                    "symbol": "KNC"
                                },
                                "FXS": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x3432B6A60D23Ca0dFCa7761B7ab56459D9C964D0",
                                    "A_TOKEN": "0x82F9c5ad306BBa1AD0De49bB5FA6F01bf61085ef",
                                    "S_TOKEN": "0x61dFd349140C239d3B61fEe203Efc811b518a317",
                                    "V_TOKEN": "0x68e9f0aD4e6f8F5DB70F6923d4d6d5b225B83b16",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x6Ebc52C8C1089be9eB3945C4350B68B8E4C2233f",
                                    "logoURI": "https://app.aave.com/icons/tokens/fxs.svg",
                                    "symbol": "FXS"
                                },
                                "crvUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf939E0A03FB07F59A73314E73794Be0E57ac1b4E",
                                    "A_TOKEN": "0xb82fa9f31612989525992FCfBB09AB22Eff5c85A",
                                    "S_TOKEN": "0xb55C604075D79486b8A329c396Fc711Be54B5330",
                                    "V_TOKEN": "0x028f7886F3e937f8479efaD64f31B3fE1119857a",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x02AeE5b225366302339748951E1a924617b8814F",
                                    "STATA_TOKEN": "0x848107491E029AFDe0AC543779c7790382f15929",
                                    "logoURI": "https://app.aave.com/icons/tokens/crvusd.svg",
                                    "symbol": "crvUSD"
                                },
                                "PYUSD": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x6c3ea9036406852006290770BEdFcAbA0e23A0e8",
                                    "A_TOKEN": "0x0C0d01AbF3e6aDfcA0989eBbA9d6e85dD58EaB1E",
                                    "S_TOKEN": "0x5B393DB4c72B1Bd82CE2834F6485d61b137Bc7aC",
                                    "V_TOKEN": "0x57B67e4DE077085Fd0AF2174e9c14871BE664546",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x150bAe7Ce224555D39AfdBc6Cb4B8204E594E022",
                                    "STATA_TOKEN": "0x00F2a835758B33f3aC53516Ebd69f3dc77B0D152",
                                    "logoURI": "https://app.aave.com/icons/tokens/pyusd.svg",
                                    "symbol": "PYUSD"
                                },
                                "weETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xCd5fE23C85820F7B72D0926FC9b05b43E359b7ee",
                                    "A_TOKEN": "0xBdfa7b7893081B35Fb54027489e2Bc7A38275129",
                                    "S_TOKEN": "0xBad6eF8e76E26F39e985474aD0974FDcabF85d37",
                                    "V_TOKEN": "0x77ad9BF13a52517AD698D65913e8D381300c8Bf3",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xf112aF6F0A332B815fbEf3Ff932c057E570b62d3",
                                    "logoURI": "https://app.aave.com/icons/tokens/weeth.svg",
                                    "symbol": "weETH"
                                },
                                "osETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf1C9acDc66974dFB6dEcB12aA385b9cD01190E38",
                                    "A_TOKEN": "0x927709711794F3De5DdBF1D176bEE2D55Ba13c21",
                                    "S_TOKEN": "0x48Fa27f511F40d16f9E7C913e9388d52d95bC6d2",
                                    "V_TOKEN": "0x8838eefF2af391863E1Bb8b1dF563F86743a8470",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x0A2AF898cEc35197e6944D9E0F525C2626393442",
                                    "logoURI": "https://app.aave.com/icons/tokens/oseth.svg",
                                    "symbol": "osETH"
                                },
                                "USDe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4c9EDD5852cd905f086C759E8383e09bff1E68B3",
                                    "A_TOKEN": "0x4F5923Fc5FD4a93352581b38B7cD26943012DECF",
                                    "S_TOKEN": "0x43Cc8AD0c223b38D9c04802bB184A2D97e497D38",
                                    "V_TOKEN": "0x015396E1F286289aE23a762088E863b3ec465145",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x55B6C4D3E8A27b8A1F5a263321b602e0fdEEcC17",
                                    "logoURI": "https://app.aave.com/icons/tokens/usde.svg",
                                    "symbol": "USDe"
                                },
                                "ETHx": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xA35b1B31Ce002FBF2058D22F30f95D405200A15b",
                                    "A_TOKEN": "0x1c0E06a0b1A4c160c17545FF2A951bfcA57C0002",
                                    "S_TOKEN": "0xBDfa7DE5CF7a7DdE4F023Cac842BF520fcF5395C",
                                    "V_TOKEN": "0x08a8Dc81AeA67F84745623aC6c72CDA3967aab8b",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xD6270dAabFe4862306190298C2B48fed9e15C847",
                                    "logoURI": "https://app.aave.com/icons/tokens/ethx.svg",
                                    "symbol": "ETHx"
                                },
                                "sUSDe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9D39A5DE30e57443BfF2A8307A4256c8797A3497",
                                    "A_TOKEN": "0x4579a27aF00A62C0EB156349f31B345c08386419",
                                    "S_TOKEN": "0xc9335dE638f4C96a8330b2FFc44353Bab58774e3",
                                    "V_TOKEN": "0xeFFDE9BFA8EC77c14C364055a200746d6e12BeD6",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xb37aE8aBa6C0C1Bf2c509fc06E11aa4AF29B665A",
                                    "logoURI": "https://app.aave.com/icons/tokens/susde.svg",
                                    "symbol": "sUSDe"
                                }
                            }
                        },
                        "10": {
                            "address": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xDA10009cBd5D07dd0CeCc66161FC93D7c9000da1",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x1a96fe91278bcF6F19665F642FE7a88cD5c360bb",
                                    "STATA_TOKEN": "0x6dDc64289bE8a71A707fB057d5d07Cc756055d6e",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x350a791Bfc2C21F9Ed5d10980Dad2e2638ffa7f6",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xCc232dcFAAE6354cE191Bd574108c1aD03f86450",
                                    "STATA_TOKEN": "0x39BCf217ACc4Bf2fCaF7BC8800E69D986912c75e",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x7F5c764cBc14f9669B88837ca1490cCa17c31607",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x2daA7078f78485A708003989cBc9a643e3b4B61f",
                                    "STATA_TOKEN": "0x9F281eb58fd98ad98EDe0fc4C553AD4D73e7Ca2C",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC.e"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x68f180fcCe6836688e9084f035309E29Bf0A2095",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xD702DD976Fb76Fffc2D3963D037dfDae5b04E593",
                                    "STATA_TOKEN": "0x6d998FeEFC7B3664eaD09CAf02b5a0fc2E365F18",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4200000000000000000000000000000000000006",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x13e3Ee699D1909E989722E753853AE30b17e08c5",
                                    "STATA_TOKEN": "0x98d69620C31869fD4822ceb6ADAB31180475FD37",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x94b008aA00579c1307B0EF2c499aD98a8ce58e58",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x70E6DBBFFc9c3c6fB4a9c349E3101B7dCEE67f4D",
                                    "STATA_TOKEN": "0x035c93db04E5aAea54E6cd0261C492a3e0638b37",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x76FB31fb4af56892A25e32cFC43De717950c9278",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x338ed6787f463394D24813b297401B9F05a8C9d1",
                                    "STATA_TOKEN": "0xae0Ca1B1Bc6cac26981B5e2b9c40f8Ce8A9082eE",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "sUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x8c6f28f2F1A3C87F0f938b96d27520d9751ec8d9",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xC77E9CF9603F5ef5503213229ABB1Fec3001f312",
                                    "STATA_TOKEN": "0x3A956E2Fcc7e71Ea14b0257d40BEbdB287d19652",
                                    "logoURI": "https://app.aave.com/icons/tokens/susd.svg",
                                    "symbol": "sUSD"
                                },
                                "OP": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4200000000000000000000000000000000000042",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x0D276FC14719f9292D5C1eA2198673d1f4269246",
                                    "STATA_TOKEN": "0xd4F1Cf9A038269FE8F03745C2875591Ad6438ab1",
                                    "logoURI": "https://app.aave.com/icons/tokens/op.svg",
                                    "symbol": "OP"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x1F32b1c2345538c0c6f582fCB022739c4A194Ebb",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x724E47194d97263ccb71FDad84b4fed18a8be387",
                                    "STATA_TOKEN": "0xb972abef80046A57409e37a7DF5dEf2638917516",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "LUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xc40F949F8a4e094D1b49a23ea9241D289B7b2819",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x8f4dAFb6Feb190e7846eb7665fD49FFb1177Ff8e",
                                    "STATA_TOKEN": "0x84648dc3Cefb601bc28a49A07a1A8Bad04D30Ad3",
                                    "logoURI": "https://app.aave.com/icons/tokens/lusd.svg",
                                    "symbol": "LUSD"
                                },
                                "MAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xdFA46478F9e5EA86d57387849598dbFB2e964b02",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xc6ac65E8f4F50a6655Efd78A92b6c503B5B625C8",
                                    "STATA_TOKEN": "0x60495bC8D8Baf7E866888ecC00491e37B47dfF24",
                                    "logoURI": "https://app.aave.com/icons/tokens/mai.svg",
                                    "symbol": "MAI"
                                },
                                "rETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9Bcef72be871e61ED4fBbc7630889beE758eb81D",
                                    "A_TOKEN": "0x724dc807b04555b71ed48a6896b6F41593b8C637",
                                    "S_TOKEN": "0xDC1fad70953Bb3918592b6fCc374fe05F5811B6a",
                                    "V_TOKEN": "0xf611aEb5013fD2c0511c9CD55c7dc5C1140741A6",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xF17e75D58D4Be71B8e674fA104B71a827e38F087",
                                    "STATA_TOKEN": "0xf9ce3c97b4b54F3D16861420f4816D9f68190B7B",
                                    "logoURI": "https://app.aave.com/icons/tokens/reth.svg",
                                    "symbol": "rETH"
                                },
                                "USDCn": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x0b2C639c533813f4Aa9D7837CAf62653d097Ff85",
                                    "A_TOKEN": "0x38d693cE1dF5AaDF7bC62595A37D667aD57922e5",
                                    "S_TOKEN": "0x8a9FdE6925a839F6B1932d16B36aC026F8d3FbdB",
                                    "V_TOKEN": "0x5D557B07776D12967914379C71a1310e917C7555",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x2daA7078f78485A708003989cBc9a643e3b4B61f",
                                    "STATA_TOKEN": "0x4DD03dfD36548C840B563745e3FBeC320F37BA7e",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                }
                            }
                        },
                        "137": {
                            "address": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x8f3Cf7ad23Cd3CaDbD9735AFf958023239c6A063",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xF86577E7d27Ed35b85A7645c58bAaA64453fe32B",
                                    "STATA_TOKEN": "0x83c59636e602787A6EEbBdA2915217B416193FcB",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x53E0bca35eC356BD5ddDFebbD1Fc0fD03FaBad39",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xd9FFdb71EbE7496cC440152d43986Aae0AB76665",
                                    "STATA_TOKEN": "0x37868a45c6741616F9E5a189dC0481AD70056B6a",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x2791Bca1f2de4661ED88A30C99A7a9449Aa84174",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x17E33D122FC34c7ad8FBd4a1995Dff9c8aE675eb",
                                    "STATA_TOKEN": "0x1017F4a86Fc3A3c824346d0b8C5e96A5029bDAf9",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC.e"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x1BFD67037B42Cf73acF2047067bd4F2C47D9BfD6",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xc907E116054Ad103354f2D350FD2514433D57F6f",
                                    "STATA_TOKEN": "0xbC0f50CCB8514Aa7dFEB297521c4BdEBc9C7d22d",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7ceB23fD6bC0adD59E62ac25578270cFf1b9f619",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xF9680D99D6C9589e2a93a78A04A279e509205945",
                                    "STATA_TOKEN": "0xb3D5Af0A52a35692D3FcbE37669b3B8C31dddE7D",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xc2132D05D31c914a87C6611C10748AEb04B58e8F",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xaA574f4f6E124E77a7a1B5Ed91c8b407000A7730",
                                    "STATA_TOKEN": "0x87A1fdc4C726c459f597282be639a045062c0E46",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD6DF932A45C0f255f85145f286eA0b292B21C90B",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x72484B12719E23115761D5DA1646945632979bB6",
                                    "STATA_TOKEN": "0xCA2E1E33E5BCF4978E2d683656E1f5610f8C4A7E",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "WMATIC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x0d500B1d8E8eF31E21C99d1Db9A6444d3ADf1270",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xAB594600376Ec9fD91F8e885dADF0CE036862dE0",
                                    "STATA_TOKEN": "0x98254592408E389D1dd2dBa318656C2C5c305b4E",
                                    "logoURI": "https://app.aave.com/icons/tokens/wmatic.svg",
                                    "symbol": "WMATIC"
                                },
                                "CRV": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x172370d5Cd63279eFa6d502DAB29171933a610AF",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x336584C8E6Dc19637A5b36206B1c79923111b405",
                                    "STATA_TOKEN": "0x4356941463eD4d75381AC23C9EF799B5d7C52AD8",
                                    "logoURI": "https://app.aave.com/icons/tokens/crv.svg",
                                    "symbol": "CRV"
                                },
                                "SUSHI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x0b3F868E0BE5597D5DB7fEB59E1CADBb0fdDa50a",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x49B0c695039243BBfEb8EcD054EB70061fd54aa0",
                                    "STATA_TOKEN": "0xe3eDe71d32240b7EC355F0e5DD1131BBe029F934",
                                    "logoURI": "https://app.aave.com/icons/tokens/sushi.svg",
                                    "symbol": "SUSHI"
                                },
                                "GHST": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x385Eeac5cB85A38A9a07A70c73e0a3271CfB54A7",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xDD229Ce42f11D8Ee7fFf29bDB71C7b81352e11be",
                                    "STATA_TOKEN": "0x123319636A6a9c85D9959399304F4cB23F64327e",
                                    "logoURI": "https://app.aave.com/icons/tokens/ghst.svg",
                                    "symbol": "GHST"
                                },
                                "BAL": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9a71012B13CA4d3D0Cdc72A177DF3ef03b0E76A3",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xD106B538F2A868c28Ca1Ec7E298C3325E0251d66",
                                    "STATA_TOKEN": "0x1a8969FD39AbaF228e690B172C4C3Eb7c67F95E1",
                                    "logoURI": "https://app.aave.com/icons/tokens/bal.svg",
                                    "symbol": "BAL"
                                },
                                "DPI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x85955046DF4668e1DD369D2DE9f3AEB98DD2A369",
                                    "A_TOKEN": "0x724dc807b04555b71ed48a6896b6F41593b8C637",
                                    "S_TOKEN": "0xDC1fad70953Bb3918592b6fCc374fe05F5811B6a",
                                    "V_TOKEN": "0xf611aEb5013fD2c0511c9CD55c7dc5C1140741A6",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x2e48b7924FBe04d575BA229A59b64547d9da16e9",
                                    "STATA_TOKEN": "0x73B788ACA5f4F0EeB3c6Da453cDf31041a77b36D",
                                    "logoURI": "https://app.aave.com/icons/tokens/dpi.svg",
                                    "symbol": "DPI"
                                },
                                "EURS": {
                                    "decimals": 2,
                                    "UNDERLYING": "0xE111178A87A3BFf0c8d18DECBa5798827539Ae99",
                                    "A_TOKEN": "0x38d693cE1dF5AaDF7bC62595A37D667aD57922e5",
                                    "S_TOKEN": "0x8a9FdE6925a839F6B1932d16B36aC026F8d3FbdB",
                                    "V_TOKEN": "0x5D557B07776D12967914379C71a1310e917C7555",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x73366Fe0AA0Ded304479862808e02506FE556a98",
                                    "STATA_TOKEN": "0x02E26888Ed3240BB38f26A2adF96Af9B52b167ea",
                                    "logoURI": "https://app.aave.com/icons/tokens/eurs.svg",
                                    "symbol": "EURS"
                                },
                                "jEUR": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4e3Decbb3645551B8A19f0eA1678079FCB33fB4c",
                                    "A_TOKEN": "0x6533afac2E7BCCB20dca161449A13A32D391fb00",
                                    "S_TOKEN": "0x6B4b37618D85Db2a7b469983C888040F7F05Ea3D",
                                    "V_TOKEN": "0x44705f578135cC5d703b4c9c122528C73Eb87145",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x73366Fe0AA0Ded304479862808e02506FE556a98",
                                    "STATA_TOKEN": "0xD992DaC78Ef3F34614E6a7d325b7b6A320FC0AB5",
                                    "logoURI": "https://app.aave.com/icons/tokens/jeur.svg",
                                    "symbol": "jEUR"
                                },
                                "EURA": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xE0B52e49357Fd4DAf2c15e02058DCE6BC0057db4",
                                    "A_TOKEN": "0x8437d7C167dFB82ED4Cb79CD44B7a32A1dd95c77",
                                    "S_TOKEN": "0x40B4BAEcc69B882e8804f9286b12228C27F8c9BF",
                                    "V_TOKEN": "0x3ca5FA07689F266e907439aFd1fBB59c44fe12f6",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x73366Fe0AA0Ded304479862808e02506FE556a98",
                                    "STATA_TOKEN": "0xd3eb8796Ed36f58E03B7b4b5AD417FA74931d2c4",
                                    "logoURI": "https://app.aave.com/icons/tokens/eura.svg",
                                    "symbol": "EURA"
                                },
                                "miMATIC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xa3Fa99A148fA48D14Ed51d610c367C61876997F1",
                                    "A_TOKEN": "0xeBe517846d0F36eCEd99C735cbF6131e1fEB775D",
                                    "S_TOKEN": "0x687871030477bf974725232F764aa04318A8b9c8",
                                    "V_TOKEN": "0x18248226C16BF76c032817854E7C83a2113B4f06",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x4ae2Ab1af7e3b0092dbF3A4B20ec3de8fC834873",
                                    "STATA_TOKEN": "0x8486B49433cCed038b51d18Ae3772CDB7E31CA5e",
                                    "logoURI": "https://app.aave.com/icons/tokens/mimatic.svg",
                                    "symbol": "miMATIC"
                                },
                                "stMATIC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x3A58a54C066FdC0f2D55FC9C89F0415C92eBf3C4",
                                    "A_TOKEN": "0xEA1132120ddcDDA2F119e99Fa7A27a0d036F7Ac9",
                                    "S_TOKEN": "0x1fFD28689DA7d0148ff0fCB669e9f9f0Fc13a219",
                                    "V_TOKEN": "0x6b030Ff3FB9956B1B69f475B77aE0d3Cf2CC5aFa",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x6D02E35031C4D99ee3A6A2BA47FaD0cFE355cA8f",
                                    "STATA_TOKEN": "0x867A180B7060fDC27610dC9096E93534F638A315",
                                    "logoURI": "https://app.aave.com/icons/tokens/stmatic.svg",
                                    "symbol": "stMATIC"
                                },
                                "MaticX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xfa68FB4628DFF1028CFEc22b4162FCcd0d45efb6",
                                    "A_TOKEN": "0x80cA0d8C38d2e2BcbaB66aA1648Bd1C7160500FE",
                                    "S_TOKEN": "0x62fC96b27a510cF4977B59FF952Dc32378Cc221d",
                                    "V_TOKEN": "0xB5b46F918C2923fC7f26DB76e8a6A6e9C4347Cf9",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xB0A72A5e454890e9715e059e8df8582a6B383DE3",
                                    "STATA_TOKEN": "0xbcDd5709641Af4BE99b1470A2B3A5203539132Ec",
                                    "logoURI": "https://app.aave.com/icons/tokens/maticx.svg",
                                    "symbol": "MaticX"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x03b54A6e9a984069379fae1a4fC4dBAE93B3bCCD",
                                    "A_TOKEN": "0xf59036CAEBeA7dC4b86638DFA2E3C97dA9FcCd40",
                                    "S_TOKEN": "0x173e54325AE58B072985DbF232436961981EA000",
                                    "V_TOKEN": "0x77fA66882a8854d883101Fb8501BD3CaD347Fc32",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xBD96b5ABBC6048c28184b462167E487533F2e35E",
                                    "STATA_TOKEN": "0x5274453F4CD5dD7280011a1Cca3B9e1b78EC59A6",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "USDCn": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x3c499c542cEF5E3811e1192ce70d8cC03d5c3359",
                                    "A_TOKEN": "0xA4D94019934D8333Ef880ABFFbF2FDd611C762BD",
                                    "S_TOKEN": "0xc889e9f8370D14A428a9857205d99BFdB400b757",
                                    "V_TOKEN": "0xE701126012EC0290822eEA17B794454d1AF8b030",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x17E33D122FC34c7ad8FBd4a1995Dff9c8aE675eb",
                                    "STATA_TOKEN": "0x2dCa80061632f3F87c9cA28364d1d0c30cD79a19",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                }
                            }
                        },
                        "534352": {
                            "address": "0x11fCfe756c05AD438e312a7fd934381537D3cFfe",
                            "ASSETS": {
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5300000000000000000000000000000000000004",
                                    "A_TOKEN": "0xf301805bE1Df81102C957f6d4Ce29d2B8c056B2a",
                                    "S_TOKEN": "0x117d9cF336287F46DBE509a43925cFF115Aa563c",
                                    "V_TOKEN": "0xfD7344CeB1Df9Cf238EcD667f4A6F99c6Ef44a56",
                                    "INTEREST_RATE_STRATEGY": "0xEC93d0BBA1b1e635ba0Fff4786dB323db49D99F0",
                                    "ORACLE": "0x6bF14CB0A831078629D993FDeBcB182b21A8774C",
                                    "STATA_TOKEN": "0x6b9DfaC194fa78a1882680E2cE19194D006AeEfd",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x06eFdBFf2a14a7c8E15944D1F4A48F9F95F663A4",
                                    "A_TOKEN": "0x1D738a3436A8C49CefFbaB7fbF04B660fb528CbD",
                                    "S_TOKEN": "0x59F359aA263f7Ac09876E869AF1F75b558904ed4",
                                    "V_TOKEN": "0x3d2E209af5BFa79297C88D6b57F89d792F6E28EE",
                                    "INTEREST_RATE_STRATEGY": "0xEC93d0BBA1b1e635ba0Fff4786dB323db49D99F0",
                                    "ORACLE": "0x427Fd98dbD1DbC2D4e792350caBe7c9665F35bee",
                                    "STATA_TOKEN": "0x9fA123bC7E6b61cC8a9D893673a4C6E5392FF4A7",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf610A9dfB7C89644979b4A0f27063E9e7d7Cda32",
                                    "A_TOKEN": "0x5B1322eeb46240b02e20062b8F0F9908d525B09c",
                                    "S_TOKEN": "0x18e3f125ce85e8D65AD2bb4f6b5fff110772A078",
                                    "V_TOKEN": "0x8a035644322129800C3f747f54Db0F4d3c0A2877",
                                    "INTEREST_RATE_STRATEGY": "0xEC93d0BBA1b1e635ba0Fff4786dB323db49D99F0",
                                    "ORACLE": "0x4EdAbf45e78363b8Dcd763bBbd05665c6e24975C",
                                    "STATA_TOKEN": "0x6e368c4dBf083e18a29aE63FC06AF9deDb3242F0",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                }
                            }
                        }
                    }
                    }//if the token is ERC20 token use this contract list and function
                    }
                },
        ```

    - LENDING_REPAY

        **Description:** Return borrowed assets to lending protocols to decrease or close debt positions, supporting full or partial repayments with interest calculations, collateral release options, and position health improvement tracking

        **Keywords:** repay loan, return borrowed, repay tokens, pay back loan, repay crypto, return loan, repay borrowed, pay off loan, repay lending, return tokens, repay debt, pay back borrowed, repay position, return debt, repay protocol, pay off borrowed, repay assets, return position, repay cryptocurrency, pay back tokens, lending repayment

        ```tsx
        {
                    "action": "LENDING_REPAY",
                    "network": "1",
                    "inputs": [
                        {
                            "name": "asset",
                            "type": "string",
                            "default": ""
                        },
                        {
                            "name": "amount",
                            "type": "string",
                            "default": ""
                        }
                    ],
                    "outputs": [
                        {
                            "name": "success",
                            "type": "boolean"
                        }
                    ],
                    "protocol": {
                "name": "AAVE"
                    "repayETH":{
                    "functionName": "repayETH",
                    "contract": {
                        "42161": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0xecD4bd3121F9FD604ffaC631bF6d41ec12f1fafb"
                        },
                        "43114": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0x2DeC8BCE3471eD65B1bB558Fa28439D45bF446d0"
                        },
                        "8453": {
                            "pool": "0xA238Dd80C259a72e81d7e4664a9801593F98d1c5",
                            "address": "0x8be473dCfA93132658821E67CbEB684ec8Ea2E74"
                        },
                        "56": {
                            "pool": "0x6807dc923806fE8Fd134338EABCA509979a7e0cB",
                            "address": "0x326aB0868bD279382Be2DF5E228Cb8AF38649AB4"
                        },
                        "1": {
                            "pool": "0x87870Bca3F3fD6335C3F4ce8392D69350B4fA4E2",
                            "address": "0x893411580e590D62dDBca8a703d61Cc4A8c7b2b9"
                        },
                        "10": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0xe9E52021f4e11DEAD8661812A0A6c8627abA2a54"
                        },
                        "137": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0xC1E320966c485ebF2A0A2A6d3c0Dc860A156eB1B"
                        },
                        "534352": {
                            "pool": "0x11fCfe756c05AD438e312a7fd934381537D3cFfe",
                            "address": "0xFF75A4B698E3Ec95E608ac0f22A03B8368E05F5D"
                        }
                    }
                    }//if the token is native token use this contract list and function

                    "repay": {
                    "functionName": "repay",
                    "contract": {
                        "42161": {
                            "address": "0x794@a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xDA10009cBd5D07dd0CeCc66161FC93D7c9000da1",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x4a838a3Dac6633bB1fd932B6f356DecFCAf7803D",
                                    "STATA_TOKEN": "0xc91c5297d7E161aCC74b482aAfCc75B85cc0bfeD",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf97f4df75117a78c1A5a0DBb814Af92458539FB4",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x86E53CF1B870786351Da77A57575e79CB55812CB",
                                    "STATA_TOKEN": "0x27dE098EF2772386cBCf1a4c8BEb886368b7F9a9",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xDe25a88F87FEd9F8999fAbF6729dCB121893623C",
                                    "STATA_TOKEN": "0x0Bc9E52051f553E75550CA22C196bf132c52Cf0B",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC.e"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x2f2a2543B76A4166549F7aaB2e75Bef0aefC5B0f",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x6ce185860a4963106506C203335A2910413708e9",
                                    "STATA_TOKEN": "0x32B95Fbe04e5a51cF99FeeF4e57Cf7e3FC9c5A93",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x82aF49447D8a07e3bd95BD0d56f35241523fBab1",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x639Fe6ab55C921f74e7fac1ee960C0B6293ba612",
                                    "STATA_TOKEN": "0x352F3475716261dCC991Bd5F2aF973eB3D0F5878",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xFd086bC7CD5C481DCC9C85ebE478A1C0b69FCbb9",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x84dC1C52D7C340AA54B4e8799FBB31C3D28E67aD",
                                    "STATA_TOKEN": "0xb165a74407fE1e519d6bCbDeC1Ed3202B35a4140",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xba5DdD1f9d7F570dc94a51479a000E3BCE967196",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xaD1d5344AaDE45F43E596773Bcc4c423EAbdD034",
                                    "STATA_TOKEN": "0x1C0c8EcED17aE093b3C1a1a8fFeBE2E9513a9346",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "EURS": {
                                    "decimals": 2,
                                    "UNDERLYING": "0xD22a58f79e9481D1a88e00c343885A588b34b68B",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xA14d53bC1F1c0F31B4aA3BD109344E5009051a84",
                                    "STATA_TOKEN": "0x9a40747BE51185A416B181789B671E78a8d045dD",
                                    "logoURI": "https://app.aave.com/icons/tokens/eurs.svg",
                                    "symbol": "EURS"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5979D7b546E38E414F7E9822514be443A4800529",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x87fE1503beFBF98C35c7526B0c488d950F822C0F",
                                    "STATA_TOKEN": "0x7775d4Ae4Dbb79a624fB96AAcDB8Ca74F671c0DF",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "MAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x3F56e0c36d275367b8C502090EDF38289b3dEa0d",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x7a7cE08a1057723CCEDeA2462407427Ae33FFEb2",
                                    "STATA_TOKEN": "0xB4a0a2692D82301703B27082Cda45B083F68CAcE",
                                    "logoURI": "https://app.aave.com/icons/tokens/mai.svg",
                                    "symbol": "MAI"
                                },
                                "rETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xEC70Dcb4A1EFa46b8F2D97C310C9c4790ba5ffA8",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x256f33FC0110B1297f78f48524631D30B752480D",
                                    "STATA_TOKEN": "0x68235105d6d33A19369D24b746cb7481FB2b34fd",
                                    "logoURI": "https://app.aave.com/icons/tokens/reth.svg",
                                    "symbol": "rETH"
                                },
                                "LUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x93b346b6BC2548dA6A1E7d98E9a421B42541425b",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x341B110bDF665A20F0D5f84A92FcAF5EbeEBC629",
                                    "STATA_TOKEN": "0xDbB6314b5b07E63B7101844c0346309B79f8C20A",
                                    "logoURI": "https://app.aave.com/icons/tokens/lusd.svg",
                                    "symbol": "LUSD"
                                },
                                "USDCn": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xaf88d065e77c8cC2239327C5EDb3A432268e5831",
                                    "A_TOKEN": "0x724dc807b04555b71ed48a6896b6F41593b8C637",
                                    "S_TOKEN": "0xDC1fad70953Bb3918592b6fCc374fe05F5811B6a",
                                    "V_TOKEN": "0xf611aEb5013fD2c0511c9CD55c7dc5C1140741A6",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xDe25a88F87FEd9F8999fAbF6729dCB121893623C",
                                    "STATA_TOKEN": "0x7CFaDFD5645B50bE87d546f42699d863648251ad",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "FRAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x17FC002b466eEc40DaE837Fc4bE5c67993ddBd6F",
                                    "A_TOKEN": "0x38d693cE1dF5AaDF7bC62595A37D667aD57922e5",
                                    "S_TOKEN": "0x8a9FdE6925a839F6B1932d16B36aC026F8d3FbdB",
                                    "V_TOKEN": "0x5D557B07776D12967914379C71a1310e917C7555",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x06919EB75Bd6BA817D38CC70C1CA588ac7a01C10",
                                    "STATA_TOKEN": "0x89AEc2023f89E26Dbb7eaa7a98fe3996f9d112A8",
                                    "logoURI": "https://app.aave.com/icons/tokens/frax.svg",
                                    "symbol": "FRAX"
                                },
                                "ARB": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x912CE59144191C1204E64559FE8253a0e49E6548",
                                    "A_TOKEN": "0x6533afac2E7BCCB20dca161449A13A32D391fb00",
                                    "S_TOKEN": "0x6B4b37618D85Db2a7b469983C888040F7F05Ea3D",
                                    "V_TOKEN": "0x44705f578135cC5d703b4c9c122528C73Eb87145",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xb2A824043730FE05F3DA2efaFa1CBbe83fa548D6",
                                    "STATA_TOKEN": "0x9b5637d7952BC9fa2D693aAE51f3103760Bf2693",
                                    "logoURI": "https://app.aave.com/icons/tokens/arb.svg",
                                    "symbol": "ARB"
                                },
                                "weETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x35751007a407ca6FEFfE80b3cB397736D2cf4dbe",
                                    "A_TOKEN": "0x8437d7C167dFB82ED4Cb79CD44B7a32A1dd95c77",
                                    "S_TOKEN": "0x40B4BAEcc69B882e8804f9286b12228C27F8c9BF",
                                    "V_TOKEN": "0x3ca5FA07689F266e907439aFd1fBB59c44fe12f6",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x517276B5972C4Db7E88B9F76Ee500E888a2D73C3",
                                    "logoURI": "https://app.aave.com/icons/tokens/weeth.svg",
                                    "symbol": "weETH"
                                },
                                "GHO": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7dfF72693f6A4149b17e7C6314655f6A9F7c8B33",
                                    "A_TOKEN": "0xeBe517846d0F36eCEd99C735cbF6131e1fEB775D",
                                    "S_TOKEN": "0x687871030477bf974725232F764aa04318A8b9c8",
                                    "V_TOKEN": "0x18248226C16BF76c032817854E7C83a2113B4f06",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xB05984aD83C20b3ADE7bf97a9a0Cb539DDE28DBb",
                                    "logoURI": "https://app.aave.com/icons/tokens/gho.svg",
                                    "symbol": "GHO"
                                }
                            }
                        },
                        "43114": {
                            "address": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAIe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xd586E7F844cEa2F87f50152665BCbc2C279D8d70",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xf82da795727633aFA9BB0f1B08A87c0F6A38723f",
                                    "STATA_TOKEN": "0x02F3f6c8A432C1e49f3359d7d36887C25d8A5888",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI.e"
                                },
                                "LINKe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5947BB275c521040051D82396192181b413227A3",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x49ccd9ca821EfEab2b98c60dC60F518E765EDe9a",
                                    "STATA_TOKEN": "0x8B773Ab77Dff01985D438961dBCE58382a70cA52",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK.e"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xB97EF9Ef8734C71904D8002F8b6Bc66Dd9c48a6E",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xD8277249e871BE9A402fa286C2C5ec16046dC512",
                                    "STATA_TOKEN": "0xC509aB7bB4eDbF193b82264D499a7Fc526Cd01F4",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "WBTCe": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x50b7545627a5162F82A992c33b87aDc75187B218",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x2779D32d5166BAaa2B2b658333bA7e6Ec0C65743",
                                    "STATA_TOKEN": "0xE3C0f42EAF1a4BFe37CbA105e5463564BA7730aE",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC.e"
                                },
                                "WETHe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x49D5c2BdFfac6CE2BFdB6640F4F80f226bc10bAB",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x976B3D034E162d8bD72D6b9C989d545b839003b0",
                                    "STATA_TOKEN": "0xf8E24175D01653fd6AA203C2C17B1e4Dd1CA2731",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH.e"
                                },
                                "USDt": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x9702230A8Ea53601f5cD2dc00fDBc13d4dF4A8c7",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x39185f2236A6022b682e8BB93C040d125DA093CF",
                                    "STATA_TOKEN": "0x5525Ee69BC1e354B356864187De486fab5AD67d7",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDt"
                                },
                                "AAVEe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x63a72806098Bd3D9520cC43356dD78afe5D386D9",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x3CA13391E9fb38a75330fb28f8cc2eB3D9ceceED",
                                    "STATA_TOKEN": "0xac0746AfD13DEbe2a43a6c8745Fb83Fd2A2909cA",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE.e"
                                },
                                "WAVAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xB31f66AA3C1e785363F0875A1B74E27b85FD66c7",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x0A77230d17318075983913bC2145DB16C7366156",
                                    "STATA_TOKEN": "0x6A02C7a974F1F13A67980C80F774eC1d2eD8f98d",
                                    "logoURI": "https://app.aave.com/icons/tokens/wavax.svg",
                                    "symbol": "WAVAX"
                                },
                                "sAVAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x2b2C81e08f1Af8835a78Bb2A90AE924ACE0eA4bE",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xB2B332f27e4B7305649a228C31Ed9858c5a6bAD9",
                                    "STATA_TOKEN": "0x4F059cA8a2a5BF8895Ee731f2E901cCB769FB95f",
                                    "logoURI": "https://app.aave.com/icons/tokens/savax.svg",
                                    "symbol": "sAVAX"
                                },
                                "FRAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD24C2Ad096400B6FBcd2ad8B24E7acBc21A1da64",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x6208576378D06ce69A27987b7A524A9B15d499a4",
                                    "STATA_TOKEN": "0xA3c2ffE702F4cD265B2249AB5f84Fab81FFf6c73",
                                    "logoURI": "https://app.aave.com/icons/tokens/frax.svg",
                                    "symbol": "FRAX"
                                },
                                "MAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5c49b268c9841AFF1Cc3B0a418ff5c3442eE3F3b",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xCcC55Db26B78a19Dba1beE0066F9c1665575439A",
                                    "STATA_TOKEN": "0x08cC59E51BB0Bc322B4D251f7262dB864d6150ce",
                                    "logoURI": "https://app.aave.com/icons/tokens/mai.svg",
                                    "symbol": "MAI"
                                },
                                "BTCb": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x152b9d0FdC40C096757F570A51E494bd4b943E50",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x2779D32d5166BAaa2B2b658333bA7e6Ec0C65743",
                                    "STATA_TOKEN": "0x34d768cc830c32DcD743321c09A2A702651bF9a2",
                                    "logoURI": "https://app.aave.com/icons/tokens/btc.svg",
                                    "symbol": "BTC.b"
                                }
                            }
                        },
                        "8453": {
                            "address": "0xA238Dd80C259a72e81d7e4664a9801593F98d1c5",
                            "ASSETS": {
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4200000000000000000000000000000000000006",
                                    "A_TOKEN": "0xD4a0e0b9149BCee3C920d2E00b5dE09138fd8bb7",
                                    "S_TOKEN": "0xaED3b56FeA82E809665f02AcBcDEc0816c75f4d9",
                                    "V_TOKEN": "0x24e6e0795b3c7c71D965fCc4f371803d1c1DcA1E",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x71041dddad3595F9CEd3DcCFBe3D1F4b0a16Bb70",
                                    "STATA_TOKEN": "0x468973e3264F2aEba0417A8f2cD0Ec397E738898",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "cbETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x2Ae3F1Ec7F1F5012CFEab0185bfc7aa3cf0DEc22",
                                    "A_TOKEN": "0xcf3D55c10DB69f28fD1A75Bd73f3D8A2d9c595ad",
                                    "S_TOKEN": "0xa9dF5c62d16d3f496673F4d736852017b086eCA0",
                                    "V_TOKEN": "0x1DabC36f19909425f654777249815c073E8Fd79F",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x8e11Ad4531826ff47BD8157a2c705F5422Da6A61",
                                    "STATA_TOKEN": "0x16A004065dfb11276DcB29Dc03fb8A85f9A43C6e",
                                    "logoURI": "https://app.aave.com/icons/tokens/cbeth.svg",
                                    "symbol": "cbETH"
                                },
                                "USDbC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xd9aAEc86B65D86f6A7B5B1b0c42FFA531710b6CA",
                                    "A_TOKEN": "0x0a1d576f3eFeF75b330424287a95A366e8281D54",
                                    "S_TOKEN": "0xBBaDd47fbaFa9dE717FE203e4707DEB893C64654",
                                    "V_TOKEN": "0x7376b2F323dC56fCd4C191B34163ac8a84702DAB",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x978D8878b53Fbe40dab7D4AB47b97AB622FFeF9f",
                                    "STATA_TOKEN": "0x6fCe2756794128B1771324caA860965801DCbCdB",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdbc.svg",
                                    "symbol": "USDbC"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xc1CBa3fCea344f92D9239c08C0568f6F2F0ee452",
                                    "A_TOKEN": "0x99CBC45ea5bb7eF3a5BC08FB1B7E56bB2442Ef0D",
                                    "S_TOKEN": "0xfe742Fa2a84294E8316F05b17c05090Fc68B5105",
                                    "V_TOKEN": "0x41A7C3f5904ad176dACbb1D99101F59ef0811DC1",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x56038D3998C42db18ba3B821bD1EbaB9B678e657",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913",
                                    "A_TOKEN": "0x4e65fE4DbA92790696d040ac24Aa414708F5c0AB",
                                    "S_TOKEN": "0x03506214379aA86ad1176af71c260278cfa10B38",
                                    "V_TOKEN": "0x59dca05b6c26dbd64b5381374aAaC5CD05644C28",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x978D8878b53Fbe40dab7D4AB47b97AB622FFeF9f",
                                    "STATA_TOKEN": "0x4EA71A20e655794051D1eE8b6e4A3269B13ccaCc",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "weETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x04C0599Ae5A44757c0af6F9eC3b93da8976c150A",
                                    "A_TOKEN": "0x7C307e128efA31F540F2E2d976C995E0B65F51F6",
                                    "S_TOKEN": "0xCBEdA45432D5325585ACAD29244f113C237B6Cf0",
                                    "V_TOKEN": "0x8D2e3F1f4b38AA9f1ceD22ac06019c7561B03901",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0xFc4d1d7a8FD1E6719e361e16044b460737F12C44",
                                    "logoURI": "https://app.aave.com/icons/tokens/weeth.svg",
                                    "symbol": "weETH"
                                }
                            }
                        },
                        "56": {
                            "address": "0x326aB0868bD279382Be2DF5E228Cb8AF38649AB4",
                            "ASSETS": {
                                "Cake": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82",
                                    "A_TOKEN": "0x4199CC1F5ed0d796563d7CcB2e036253E2C18281",
                                    "S_TOKEN": "0x57e95511de39890D3e782df4b19F0D97A05DF64A",
                                    "V_TOKEN": "0xE20dBC7119c635B1B51462f844861258770e0699",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0xB6064eD41d4f67e353768aA239cA86f4F73665a1",
                                    "STATA_TOKEN": "0x3854354CE3681da1D7F550073061E92a4a7d1B27",
                                    "logoURI": "https://app.aave.com/icons/tokens/cake.svg",
                                    "symbol": "Cake"
                                },
                                "WBNB": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xbb4CdB9CBd36B01bD1cBaEBF2De08d9173bc095c",
                                    "A_TOKEN": "0x9B00a09492a626678E5A3009982191586C444Df9",
                                    "S_TOKEN": "0x5cc46d2b1103aB23CFD63eF8631480bbf4eB40FE",
                                    "V_TOKEN": "0x0E76414d433ddfe8004d2A7505d218874875a996",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x0567F2323251f0Aab15c8dFb1967E4e8A7D42aeE",
                                    "STATA_TOKEN": "0x436baCb4C66583de4Cb16e13a1A0D9A3075DE425",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbnb.svg",
                                    "symbol": "WBNB"
                                },
                                "BTCB": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7130d2A12B9BCbFAe4f2634d864A1Ee1Ce3Ead9c",
                                    "A_TOKEN": "0x56a7ddc4e848EbF43845854205ad71D5D5F72d3D",
                                    "S_TOKEN": "0x9Ef6D76740713C674A6e4f38B863E62D10965053",
                                    "V_TOKEN": "0x7b1E82F4f542fbB25D64c5523Fe3e44aBe4F2702",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x264990fbd0A4796A3E3d8E37C4d5F87a3aCa5Ebf",
                                    "STATA_TOKEN": "0x1F66b530084079d35478A069d9c4424F9c9C320c",
                                    "logoURI": "https://app.aave.com/icons/tokens/btcb.svg",
                                    "symbol": "BTCB"
                                },
                                "ETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x2170Ed0880ac9A755fd29B2688956BD959F933F8",
                                    "A_TOKEN": "0x2E94171493fAbE316b6205f1585779C887771E2F",
                                    "S_TOKEN": "0xa8327EE1858E06983af6690d24e77774807109d4",
                                    "V_TOKEN": "0x8FDea7891b4D6dbdc746309245B316aF691A636C",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x9ef1B8c0E4F7dc8bF5719Ea496883DC6401d5b2e",
                                    "STATA_TOKEN": "0x52077433fB7053D747E2846aD0C18ff5015C368E",
                                    "logoURI": "https://app.aave.com/icons/tokens/eth.svg",
                                    "symbol": "ETH"
                                },
                                "USDC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x8AC76a51cc950d9822D68b83fE1Ad97B32Cd580d",
                                    "A_TOKEN": "0x00901a076785e0906d1028c7d6372d247bec7d61",
                                    "S_TOKEN": "0xCcC260D9778F900eAd566Fa2E1D622E667677653",
                                    "V_TOKEN": "0xcDBBEd5606d9c5C98eEedd67933991dC17F0c68d",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0xaFcFF74AE956f4c23c27Db49659D4a7F350415C1",
                                    "STATA_TOKEN": "0x3906cDdfb781f02B21f21BD81ed7Fd8DC37075E1",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "USDT": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x55d398326f99059fF775485246999027B3197955",
                                    "A_TOKEN": "0xa9251ca9DE909CB71783723713B21E4233fbf1B1",
                                    "S_TOKEN": "0xB735D922a36d4337f561CE433594727e1bc8bD01",
                                    "V_TOKEN": "0xF8bb2Be50647447Fb355e3a77b81be4db64107cd",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x0F682319Ed4A240b7a2599A48C965049515D9bC3",
                                    "STATA_TOKEN": "0x0471D185cc7Be61E154277cAB2396cD397663da6",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "FDUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xc5f0f7b66764F6ec8C8Dff7BA683102295E16409",
                                    "A_TOKEN": "0x75bd1A659bdC62e4C313950d44A2416faB43E785",
                                    "S_TOKEN": "0x5543d347bfae77A5FF913e589aB6D6ad520f1C73",
                                    "V_TOKEN": "0xE628B8a123e6037f1542e662B9F55141a16945C8",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x60a117Fa5bAbee4d645884fB11E413Da4F893b6D",
                                    "STATA_TOKEN": "0x4d074aAa0821073dA827f7bf6a02cF905b394ed0",
                                    "logoURI": "https://app.aave.com/icons/tokens/fdusd.svg",
                                    "symbol": "FDUSD"
                                }
                            }
                        },
                        "1": {
                            "address": "0x87870Bca3F3fD6335C3F4ce8392D69350B4fA4E2",
                            "ASSETS": {
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2",
                                    "A_TOKEN": "0x4d5F47FA6A74757f35C14fD3a6Ef8E3C9BC514E8",
                                    "S_TOKEN": "0x102633152313C81cD80419b6EcF66d14Ad68949A",
                                    "V_TOKEN": "0xeA51d7853EEFb32b6ee06b1C12E6dcCA88Be0fFE",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x5f4eC3Df9cbd43714FE2740f5E3616155c5b8419",
                                    "STATA_TOKEN": "0x252231882FB38481497f3C767469106297c8d93b",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7f39C581F595B53c5cb19bD0b3f8dA6c935E2Ca0",
                                    "A_TOKEN": "0x0B925eD163218f6662a35e0f0371Ac234f9E9371",
                                    "S_TOKEN": "0x39739943199c0fBFe9E5f1B5B160cd73a64CB85D",
                                    "V_TOKEN": "0xC96113eED8cAB59cD8A66813bCB0cEb29F06D2e4",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xB4aB0c94159bc2d8C133946E7241368fc2F2a010",
                                    "STATA_TOKEN": "0x322AA5F5Be95644d6c36544B6c5061F072D16DF5",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x2260FAC5E5542a773Aa44fBCfeDf7C193bc2C599",
                                    "A_TOKEN": "0x5Ee5bf7ae06D1Be5997A1A72006FE6C607eC6DE8",
                                    "S_TOKEN": "0xA1773F1ccF6DB192Ad8FE826D15fe1d328B03284",
                                    "V_TOKEN": "0x40aAbEf1aa8f0eEc637E0E7d92fbfFB2F26A8b7B",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x230E0321Cf38F09e247e50Afc7801EA2351fe56F",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48",
                                    "A_TOKEN": "0x98C23E9d8f34FEFb1B7BD6a91B7FF122F4e16F5c",
                                    "S_TOKEN": "0xB0fe3D292f4bd50De902Ba5bDF120Ad66E9d7a39",
                                    "V_TOKEN": "0x72E95b8931767C79bA4EeE721354d6E99a61D004",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x736bF902680e68989886e9807CD7Db4B3E015d3C",
                                    "STATA_TOKEN": "0x73edDFa87C71ADdC275c2b9890f5c3a8480bC9E6",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x6B175474E89094C44Da98b954EedeAC495271d0F",
                                    "A_TOKEN": "0x018008bfb33d285247A21d44E50697654f754e63",
                                    "S_TOKEN": "0x413AdaC9E2Ef8683ADf5DDAEce8f19613d60D1bb",
                                    "V_TOKEN": "0xcF8d0c70c850859266f5C338b38F9D663181C314",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xaEb897E1Dc6BbdceD3B9D551C71a8cf172F27AC4",
                                    "STATA_TOKEN": "0xaf270C38fF895EA3f95Ed488CEACe2386F038249",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x514910771AF9Ca656af840dff83E8264EcF986CA",
                                    "A_TOKEN": "0x5E8C8A7243651DB1384C0dDfDbE39761E8e7E51a",
                                    "S_TOKEN": "0x63B1129ca97D2b9F97f45670787Ac12a9dF1110a",
                                    "V_TOKEN": "0x4228F8895C7dDA20227F6a5c6751b8Ebf19a6ba8",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x2c1d072e956AFFC0D435Cb7AC38EF18d24d9127c",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7Fc66500c84A76Ad7e9c93437bFc5Ac33E2DDaE9",
                                    "A_TOKEN": "0xA700b4eB416Be35b2911fd5Dee80678ff64fF6C9",
                                    "S_TOKEN": "0x268497bF083388B1504270d0E717222d3A87D6F2",
                                    "V_TOKEN": "0xBae535520Abd9f8C85E58929e0006A2c8B372F74",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x547a514d5e3769680Ce22B2361c10Ea13619e8a9",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "cbETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xBe9895146f7AF43049ca1c1AE358B0541Ea49704",
                                    "A_TOKEN": "0x977b6fc5dE62598B08C85AC8Cf2b745874E8b78c",
                                    "S_TOKEN": "0x82bE6012cea6D147B968eBAea5ceEcF6A5b4F493",
                                    "V_TOKEN": "0x0c91bcA95b5FE69164cE583A2ec9429A569798Ed",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x6243d2F41b4ec944F731f647589E28d9745a2674",
                                    "logoURI": "https://app.aave.com/icons/tokens/cbeth.svg",
                                    "symbol": "cbETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xdAC17F958D2ee523a2206206994597C13D831ec7",
                                    "A_TOKEN": "0x23878914EFE38d27C4D67Ab83ed1b93A74D4086a",
                                    "S_TOKEN": "0x822Fa72Df1F229C3900f5AD6C3Fa2C424D691622",
                                    "V_TOKEN": "0x6df1C1E379bC5a00a7b4C6e67A203333772f45A8",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xC26D4a1c46d884cfF6dE9800B6aE7A8Cf48B4Ff8",
                                    "STATA_TOKEN": "0x862c57d48becB45583AEbA3f489696D22466Ca1b",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "rETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xae78736Cd615f374D3085123A210448E74Fc6393",
                                    "A_TOKEN": "0xCc9EE9483f662091a1de4795249E24aC0aC2630f",
                                    "S_TOKEN": "0x1d1906f909CAe494c7441604DAfDDDbD0485A925",
                                    "V_TOKEN": "0xae8593DD575FE29A9745056aA91C4b746eee62C8",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x5AE8365D0a30D67145f0c55A08760C250559dB64",
                                    "logoURI": "https://app.aave.com/icons/tokens/reth.svg",
                                    "symbol": "rETH"
                                },
                                "LUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5f98805A4E8be255a32880FDeC7F6728C6568bA0",
                                    "A_TOKEN": "0x3Fe6a295459FAe07DF8A0ceCC36F37160FE86AA9",
                                    "S_TOKEN": "0x37A6B708FDB1483C231961b9a7F145261E815fc3",
                                    "V_TOKEN": "0x33652e48e4B74D18520f11BfE58Edd2ED2cEc5A2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x9eCdfaCca946614cc32aF63F3DBe50959244F3af",
                                    "STATA_TOKEN": "0xDBf5E36569798D1E39eE9d7B1c61A7409a74F23A",
                                    "logoURI": "https://app.aave.com/icons/tokens/lusd.svg",
                                    "symbol": "LUSD"
                                },
                                "CRV": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD533a949740bb3306d119CC777fa900bA034cd52",
                                    "A_TOKEN": "0x7B95Ec873268a6BFC6427e7a28e396Db9D0ebc65",
                                    "S_TOKEN": "0x90D9CD005E553111EB8C9c31Abe9706a186b6048",
                                    "V_TOKEN": "0x1b7D3F4b3c032a5AE656e30eeA4e8E1Ba376068F",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xCd627aA160A6fA45Eb793D19Ef54f5062F20f33f",
                                    "logoURI": "https://app.aave.com/icons/tokens/crv.svg",
                                    "symbol": "CRV"
                                },
                                "MKR": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9f8F72aA9304c8B593d555F12eF6589cC3A579A2",
                                    "A_TOKEN": "0x8A458A9dc9048e005d22849F470891b840296619",
                                    "S_TOKEN": "0x0496372BE7e426D28E89DEBF01f19F014d5938bE",
                                    "V_TOKEN": "0x6Efc73E54E41b27d2134fF9f98F15550f30DF9B1",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xec1D1B3b0443256cc3860e24a46F108e699484Aa",
                                    "logoURI": "https://app.aave.com/icons/tokens/mkr.svg",
                                    "symbol": "MKR"
                                },
                                "SNX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xC011a73ee8576Fb46F5E1c5751cA3B9Fe0af2a6F",
                                    "A_TOKEN": "0xC7B4c17861357B8ABB91F25581E7263E08DCB59c",
                                    "S_TOKEN": "0x478E1ec1A2BeEd94c1407c951E4B9e22d53b2501",
                                    "V_TOKEN": "0x8d0de040e8aAd872eC3c33A3776dE9152D3c34ca",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xDC3EA94CD0AC27d9A86C180091e7f78C683d3699",
                                    "logoURI": "https://app.aave.com/icons/tokens/snx.svg",
                                    "symbol": "SNX"
                                },
                                "BAL": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xba100000625a3754423978a60c9317c58a424e3D",
                                    "A_TOKEN": "0x2516E7B3F76294e03C42AA4c5b5b4DCE9C436fB8",
                                    "S_TOKEN": "0xB368d45aaAa07ee2c6275Cb320D140b22dE43CDD",
                                    "V_TOKEN": "0x3D3efceb4Ff0966D34d9545D3A2fa2dcdBf451f2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xdF2917806E30300537aEB49A7663062F4d1F2b5F",
                                    "logoURI": "https://app.aave.com/icons/tokens/bal.svg",
                                    "symbol": "BAL"
                                },
                                "UNI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x1f9840a85d5aF5bf1D1762F925BDADdC4201F984",
                                    "A_TOKEN": "0xF6D2224916DDFbbab6e6bd0D1B7034f4Ae0CaB18",
                                    "S_TOKEN": "0x2FEc76324A0463c46f32e74A86D1cf94C02158DC",
                                    "V_TOKEN": "0xF64178Ebd2E2719F2B1233bCb5Ef6DB4bCc4d09a",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x553303d460EE0afB37EdFf9bE42922D8FF63220e",
                                    "logoURI": "https://app.aave.com/icons/tokens/uni.svg",
                                    "symbol": "UNI"
                                },
                                "LDO": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5A98FcBEA516Cf06857215779Fd812CA3beF1B32",
                                    "A_TOKEN": "0x9A44fd41566876A39655f74971a3A6eA0a17a454",
                                    "S_TOKEN": "0xa0a5bF5781Aeb548db9d4226363B9e89287C5FD2",
                                    "V_TOKEN": "0xc30808705C01289A3D306ca9CAB081Ba9114eC82",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xb01e6C9af83879B8e06a092f0DD94309c0D497E4",
                                    "logoURI": "https://app.aave.com/icons/tokens/ldo.svg",
                                    "symbol": "LDO"
                                },
                                "ENS": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xC18360217D8F7Ab5e7c516566761Ea12Ce7F9D72",
                                    "A_TOKEN": "0x545bD6c032eFdde65A377A6719DEF2796C8E0f2e",
                                    "S_TOKEN": "0x7617d02E311CdE347A0cb45BB7DF2926BBaf5347",
                                    "V_TOKEN": "0xd180D7fdD4092f07428eFE801E17BC03576b3192",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x5C00128d4d1c2F4f652C267d7bcdD7aC99C16E16",
                                    "logoURI": "https://app.aave.com/icons/tokens/ens.svg",
                                    "symbol": "ENS"
                                },
                                "ONE_INCH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x111111111117dC0aa78b770fA6A738034120C302",
                                    "A_TOKEN": "0x71Aef7b30728b9BB371578f36c5A1f1502a5723e",
                                    "S_TOKEN": "0x4b62bFAff61AB3985798e5202D2d167F567D0BCD",
                                    "V_TOKEN": "0xA38fCa8c6Bf9BdA52E76EB78f08CaA3BE7c5A970",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xc929ad75B72593967DE83E7F7Cda0493458261D9",
                                    "logoURI": "https://app.aave.com/icons/tokens/1inch.svg",
                                    "symbol": "1INCH"
                                },
                                "FRAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x853d955aCEf822Db058eb8505911ED77F175b99e",
                                    "A_TOKEN": "0xd4e245848d6E1220DBE62e155d89fa327E43CB06",
                                    "S_TOKEN": "0x219640546c0DFDDCb9ab3bcdA89B324e0a376367",
                                    "V_TOKEN": "0x88B8358F5BC87c2D7E116cCA5b65A9eEb2c5EA3F",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x45D270263BBee500CF8adcf2AbC0aC227097b036",
                                    "STATA_TOKEN": "0xEE66abD4D0f9908A48E08AE354B0f425De3e237E",
                                    "logoURI": "https://app.aave.com/icons/tokens/frax.svg",
                                    "symbol": "FRAX"
                                },
                                "GHO": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x40D16FC0246aD3160Ccc09B8D0D3A2cD28aE6C2f",
                                    "A_TOKEN": "0x00907f9921424583e7ffBfEdf84F92B7B2Be4977",
                                    "S_TOKEN": "0x3f3DF7266dA30102344A813F1a3D07f5F041B5AC",
                                    "V_TOKEN": "0x786dBff3f1292ae8F92ea68Cf93c30b34B1ed04B",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xD110cac5d8682A3b045D5524a9903E031d70FCCd",
                                    "logoURI": "https://app.aave.com/icons/tokens/gho.svg",
                                    "symbol": "GHO"
                                },
                                "RPL": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD33526068D116cE69F19A9ee46F0bd304F21A51f",
                                    "A_TOKEN": "0xB76CF92076adBF1D9C39294FA8e7A67579FDe357",
                                    "S_TOKEN": "0x41e330fd8F7eA31E2e8F02cC0C9392D1403597B4",
                                    "V_TOKEN": "0x8988ECA19D502fd8b9CCd03fA3bD20a6f599bc2A",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x4E155eD98aFE9034b7A5962f6C84c86d869daA9d",
                                    "logoURI": "https://app.aave.com/icons/tokens/rpl.svg",
                                    "symbol": "RPL"
                                },
                                "sDAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x83F20F44975D03b1b09e64809B757c47f942BEeA",
                                    "A_TOKEN": "0x4C612E3B15b96Ff9A6faED838F8d07d479a8dD4c",
                                    "S_TOKEN": "0x48Bc45f084988bC01933EA93EeFfEBC0416534f6",
                                    "V_TOKEN": "0x8Db9D35e117d8b93C6Ca9b644b25BaD5d9908141",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x29081f7aB5a644716EfcDC10D5c926c5fEe9F72B",
                                    "logoURI": "https://app.aave.com/icons/tokens/sdai.svg",
                                    "symbol": "sDAI"
                                },
                                "STG": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xAf5191B0De278C7286d6C7CC6ab6BB8A73bA2Cd6",
                                    "A_TOKEN": "0x1bA9843bD4327c6c77011406dE5fA8749F7E3479",
                                    "S_TOKEN": "0xc3115D0660b93AeF10F298886ae22E3Dd477E482",
                                    "V_TOKEN": "0x655568bDd6168325EC7e58Bf39b21A856F906Dc2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x7A9f34a0Aa917D438e9b6E630067062B7F8f6f3d",
                                    "logoURI": "https://app.aave.com/icons/tokens/stg.svg",
                                    "symbol": "STG"
                                },
                                "KNC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xdeFA4e8a7bcBA345F687a2f1456F5Edd9CE97202",
                                    "A_TOKEN": "0x5b502e3796385E1e9755d7043B9C945C3aCCeC9C",
                                    "S_TOKEN": "0xdfEE0C9eA1309cB9611F33972E72a72166fcF548",
                                    "V_TOKEN": "0x253127Ffc04981cEA8932F406710661c2f2c3fD2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xf8fF43E991A81e6eC886a3D281A2C6cC19aE70Fc",
                                    "logoURI": "https://app.aave.com/icons/tokens/knc.svg",
                                    "symbol": "KNC"
                                },
                                "FXS": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x3432B6A60D23Ca0dFCa7761B7ab56459D9C964D0",
                                    "A_TOKEN": "0x82F9c5ad306BBa1AD0De49bB5FA6F01bf61085ef",
                                    "S_TOKEN": "0x61dFd349140C239d3B61fEe203Efc811b518a317",
                                    "V_TOKEN": "0x68e9f0aD4e6f8F5DB70F6923d4d6d5b225B83b16",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x6Ebc52C8C1089be9eB3945C4350B68B8E4C2233f",
                                    "logoURI": "https://app.aave.com/icons/tokens/fxs.svg",
                                    "symbol": "FXS"
                                },
                                "crvUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf939E0A03FB07F59A73314E73794Be0E57ac1b4E",
                                    "A_TOKEN": "0xb82fa9f31612989525992FCfBB09AB22Eff5c85A",
                                    "S_TOKEN": "0xb55C604075D79486b8A329c396Fc711Be54B5330",
                                    "V_TOKEN": "0x028f7886F3e937f8479efaD64f31B3fE1119857a",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x02AeE5b225366302339748951E1a924617b8814F",
                                    "STATA_TOKEN": "0x848107491E029AFDe0AC543779c7790382f15929",
                                    "logoURI": "https://app.aave.com/icons/tokens/crvusd.svg",
                                    "symbol": "crvUSD"
                                },
                                "PYUSD": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x6c3ea9036406852006290770BEdFcAbA0e23A0e8",
                                    "A_TOKEN": "0x0C0d01AbF3e6aDfcA0989eBbA9d6e85dD58EaB1E",
                                    "S_TOKEN": "0x5B393DB4c72B1Bd82CE2834F6485d61b137Bc7aC",
                                    "V_TOKEN": "0x57B67e4DE077085Fd0AF2174e9c14871BE664546",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x150bAe7Ce224555D39AfdBc6Cb4B8204E594E022",
                                    "STATA_TOKEN": "0x00F2a835758B33f3aC53516Ebd69f3dc77B0D152",
                                    "logoURI": "https://app.aave.com/icons/tokens/pyusd.svg",
                                    "symbol": "PYUSD"
                                },
                                "weETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xCd5fE23C85820F7B72D0926FC9b05b43E359b7ee",
                                    "A_TOKEN": "0xBdfa7b7893081B35Fb54027489e2Bc7A38275129",
                                    "S_TOKEN": "0xBad6eF8e76E26F39e985474aD0974FDcabF85d37",
                                    "V_TOKEN": "0x77ad9BF13a52517AD698D65913e8D381300c8Bf3",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xf112aF6F0A332B815fbEf3Ff932c057E570b62d3",
                                    "logoURI": "https://app.aave.com/icons/tokens/weeth.svg",
                                    "symbol": "weETH"
                                },
                                "osETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf1C9acDc66974dFB6dEcB12aA385b9cD01190E38",
                                    "A_TOKEN": "0x927709711794F3De5DdBF1D176bEE2D55Ba13c21",
                                    "S_TOKEN": "0x48Fa27f511F40d16f9E7C913e9388d52d95bC6d2",
                                    "V_TOKEN": "0x8838eefF2af391863E1Bb8b1dF563F86743a8470",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x0A2AF898cEc35197e6944D9E0F525C2626393442",
                                    "logoURI": "https://app.aave.com/icons/tokens/oseth.svg",
                                    "symbol": "osETH"
                                },
                                "USDe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4c9EDD5852cd905f086C759E8383e09bff1E68B3",
                                    "A_TOKEN": "0x4F5923Fc5FD4a93352581b38B7cD26943012DECF",
                                    "S_TOKEN": "0x43Cc8AD0c223b38D9c04802bB184A2D97e497D38",
                                    "V_TOKEN": "0x015396E1F286289aE23a762088E863b3ec465145",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x55B6C4D3E8A27b8A1F5a263321b602e0fdEEcC17",
                                    "logoURI": "https://app.aave.com/icons/tokens/usde.svg",
                                    "symbol": "USDe"
                                },
                                "ETHx": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xA35b1B31Ce002FBF2058D22F30f95D405200A15b",
                                    "A_TOKEN": "0x1c0E06a0b1A4c160c17545FF2A951bfcA57C0002",
                                    "S_TOKEN": "0xBDfa7DE5CF7a7DdE4F023Cac842BF520fcF5395C",
                                    "V_TOKEN": "0x08a8Dc81AeA67F84745623aC6c72CDA3967aab8b",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xD6270dAabFe4862306190298C2B48fed9e15C847",
                                    "logoURI": "https://app.aave.com/icons/tokens/ethx.svg",
                                    "symbol": "ETHx"
                                },
                                "sUSDe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9D39A5DE30e57443BfF2A8307A4256c8797A3497",
                                    "A_TOKEN": "0x4579a27aF00A62C0EB156349f31B345c08386419",
                                    "S_TOKEN": "0xc9335dE638f4C96a8330b2FFc44353Bab58774e3",
                                    "V_TOKEN": "0xeFFDE9BFA8EC77c14C364055a200746d6e12BeD6",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xb37aE8aBa6C0C1Bf2c509fc06E11aa4AF29B665A",
                                    "logoURI": "https://app.aave.com/icons/tokens/susde.svg",
                                    "symbol": "sUSDe"
                                }
                            }
                        },
                        "10": {
                            "address": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xDA10009cBd5D07dd0CeCc66161FC93D7c9000da1",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x1a96fe91278bcF6F19665F642FE7a88cD5c360bb",
                                    "STATA_TOKEN": "0x6dDc64289bE8a71A707fB057d5d07Cc756055d6e",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x350a791Bfc2C21F9Ed5d10980Dad2e2638ffa7f6",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xCc232dcFAAE6354cE191Bd574108c1aD03f86450",
                                    "STATA_TOKEN": "0x39BCf217ACc4Bf2fCaF7BC8800E69D986912c75e",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x7F5c764cBc14f9669B88837ca1490cCa17c31607",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x2daA7078f78485A708003989cBc9a643e3b4B61f",
                                    "STATA_TOKEN": "0x9F281eb58fd98ad98EDe0fc4C553AD4D73e7Ca2C",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC.e"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x68f180fcCe6836688e9084f035309E29Bf0A2095",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xD702DD976Fb76Fffc2D3963D037dfDae5b04E593",
                                    "STATA_TOKEN": "0x6d998FeEFC7B3664eaD09CAf02b5a0fc2E365F18",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4200000000000000000000000000000000000006",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x13e3Ee699D1909E989722E753853AE30b17e08c5",
                                    "STATA_TOKEN": "0x98d69620C31869fD4822ceb6ADAB31180475FD37",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x94b008aA00579c1307B0EF2c499aD98a8ce58e58",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x70E6DBBFFc9c3c6fB4a9c349E3101B7dCEE67f4D",
                                    "STATA_TOKEN": "0x035c93db04E5aAea54E6cd0261C492a3e0638b37",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x76FB31fb4af56892A25e32cFC43De717950c9278",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x338ed6787f463394D24813b297401B9F05a8C9d1",
                                    "STATA_TOKEN": "0xae0Ca1B1Bc6cac26981B5e2b9c40f8Ce8A9082eE",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "sUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x8c6f28f2F1A3C87F0f938b96d27520d9751ec8d9",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xC77E9CF9603F5ef5503213229ABB1Fec3001f312",
                                    "STATA_TOKEN": "0x3A956E2Fcc7e71Ea14b0257d40BEbdB287d19652",
                                    "logoURI": "https://app.aave.com/icons/tokens/susd.svg",
                                    "symbol": "sUSD"
                                },
                                "OP": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4200000000000000000000000000000000000042",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x0D276FC14719f9292D5C1eA2198673d1f4269246",
                                    "STATA_TOKEN": "0xd4F1Cf9A038269FE8F03745C2875591Ad6438ab1",
                                    "logoURI": "https://app.aave.com/icons/tokens/op.svg",
                                    "symbol": "OP"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x1F32b1c2345538c0c6f582fCB022739c4A194Ebb",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x724E47194d97263ccb71FDad84b4fed18a8be387",
                                    "STATA_TOKEN": "0xb972abef80046A57409e37a7DF5dEf2638917516",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "LUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xc40F949F8a4e094D1b49a23ea9241D289B7b2819",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x8f4dAFb6Feb190e7846eb7665fD49FFb1177Ff8e",
                                    "STATA_TOKEN": "0x84648dc3Cefb601bc28a49A07a1A8Bad04D30Ad3",
                                    "logoURI": "https://app.aave.com/icons/tokens/lusd.svg",
                                    "symbol": "LUSD"
                                },
                                "MAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xdFA46478F9e5EA86d57387849598dbFB2e964b02",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xc6ac65E8f4F50a6655Efd78A92b6c503B5B625C8",
                                    "STATA_TOKEN": "0x60495bC8D8Baf7E866888ecC00491e37B47dfF24",
                                    "logoURI": "https://app.aave.com/icons/tokens/mai.svg",
                                    "symbol": "MAI"
                                },
                                "rETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9Bcef72be871e61ED4fBbc7630889beE758eb81D",
                                    "A_TOKEN": "0x724dc807b04555b71ed48a6896b6F41593b8C637",
                                    "S_TOKEN": "0xDC1fad70953Bb3918592b6fCc374fe05F5811B6a",
                                    "V_TOKEN": "0xf611aEb5013fD2c0511c9CD55c7dc5C1140741A6",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xF17e75D58D4Be71B8e674fA104B71a827e38F087",
                                    "STATA_TOKEN": "0xf9ce3c97b4b54F3D16861420f4816D9f68190B7B",
                                    "logoURI": "https://app.aave.com/icons/tokens/reth.svg",
                                    "symbol": "rETH"
                                },
                                "USDCn": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x0b2C639c533813f4Aa9D7837CAf62653d097Ff85",
                                    "A_TOKEN": "0x38d693cE1dF5AaDF7bC62595A37D667aD57922e5",
                                    "S_TOKEN": "0x8a9FdE6925a839F6B1932d16B36aC026F8d3FbdB",
                                    "V_TOKEN": "0x5D557B07776D12967914379C71a1310e917C7555",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x2daA7078f78485A708003989cBc9a643e3b4B61f",
                                    "STATA_TOKEN": "0x4DD03dfD36548C840B563745e3FBeC320F37BA7e",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                }
                            }
                        },
                        "137": {
                            "address": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x8f3Cf7ad23Cd3CaDbD9735AFf958023239c6A063",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xF86577E7d27Ed35b85A7645c58bAaA64453fe32B",
                                    "STATA_TOKEN": "0x83c59636e602787A6EEbBdA2915217B416193FcB",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x53E0bca35eC356BD5ddDFebbD1Fc0fD03FaBad39",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xd9FFdb71EbE7496cC440152d43986Aae0AB76665",
                                    "STATA_TOKEN": "0x37868a45c6741616F9E5a189dC0481AD70056B6a",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x2791Bca1f2de4661ED88A30C99A7a9449Aa84174",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x17E33D122FC34c7ad8FBd4a1995Dff9c8aE675eb",
                                    "STATA_TOKEN": "0x1017F4a86Fc3A3c824346d0b8C5e96A5029bDAf9",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC.e"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x1BFD67037B42Cf73acF2047067bd4F2C47D9BfD6",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xc907E116054Ad103354f2D350FD2514433D57F6f",
                                    "STATA_TOKEN": "0xbC0f50CCB8514Aa7dFEB297521c4BdEBc9C7d22d",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7ceB23fD6bC0adD59E62ac25578270cFf1b9f619",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xF9680D99D6C9589e2a93a78A04A279e509205945",
                                    "STATA_TOKEN": "0xb3D5Af0A52a35692D3FcbE37669b3B8C31dddE7D",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xc2132D05D31c914a87C6611C10748AEb04B58e8F",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xaA574f4f6E124E77a7a1B5Ed91c8b407000A7730",
                                    "STATA_TOKEN": "0x87A1fdc4C726c459f597282be639a045062c0E46",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD6DF932A45C0f255f85145f286eA0b292B21C90B",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x72484B12719E23115761D5DA1646945632979bB6",
                                    "STATA_TOKEN": "0xCA2E1E33E5BCF4978E2d683656E1f5610f8C4A7E",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "WMATIC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x0d500B1d8E8eF31E21C99d1Db9A6444d3ADf1270",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xAB594600376Ec9fD91F8e885dADF0CE036862dE0",
                                    "STATA_TOKEN": "0x98254592408E389D1dd2dBa318656C2C5c305b4E",
                                    "logoURI": "https://app.aave.com/icons/tokens/wmatic.svg",
                                    "symbol": "WMATIC"
                                },
                                "CRV": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x172370d5Cd63279eFa6d502DAB29171933a610AF",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x336584C8E6Dc19637A5b36206B1c79923111b405",
                                    "STATA_TOKEN": "0x4356941463eD4d75381AC23C9EF799B5d7C52AD8",
                                    "logoURI": "https://app.aave.com/icons/tokens/crv.svg",
                                    "symbol": "CRV"
                                },
                                "SUSHI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x0b3F868E0BE5597D5DB7fEB59E1CADBb0fdDa50a",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x49B0c695039243BBfEb8EcD054EB70061fd54aa0",
                                    "STATA_TOKEN": "0xe3eDe71d32240b7EC355F0e5DD1131BBe029F934",
                                    "logoURI": "https://app.aave.com/icons/tokens/sushi.svg",
                                    "symbol": "SUSHI"
                                },
                                "GHST": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x385Eeac5cB85A38A9a07A70c73e0a3271CfB54A7",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xDD229Ce42f11D8Ee7fFf29bDB71C7b81352e11be",
                                    "STATA_TOKEN": "0x123319636A6a9c85D9959399304F4cB23F64327e",
                                    "logoURI": "https://app.aave.com/icons/tokens/ghst.svg",
                                    "symbol": "GHST"
                                },
                                "BAL": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9a71012B13CA4d3D0Cdc72A177DF3ef03b0E76A3",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xD106B538F2A868c28Ca1Ec7E298C3325E0251d66",
                                    "STATA_TOKEN": "0x1a8969FD39AbaF228e690B172C4C3Eb7c67F95E1",
                                    "logoURI": "https://app.aave.com/icons/tokens/bal.svg",
                                    "symbol": "BAL"
                                },
                                "DPI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x85955046DF4668e1DD369D2DE9f3AEB98DD2A369",
                                    "A_TOKEN": "0x724dc807b04555b71ed48a6896b6F41593b8C637",
                                    "S_TOKEN": "0xDC1fad70953Bb3918592b6fCc374fe05F5811B6a",
                                    "V_TOKEN": "0xf611aEb5013fD2c0511c9CD55c7dc5C1140741A6",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x2e48b7924FBe04d575BA229A59b64547d9da16e9",
                                    "STATA_TOKEN": "0x73B788ACA5f4F0EeB3c6Da453cDf31041a77b36D",
                                    "logoURI": "https://app.aave.com/icons/tokens/dpi.svg",
                                    "symbol": "DPI"
                                },
                                "EURS": {
                                    "decimals": 2,
                                    "UNDERLYING": "0xE111178A87A3BFf0c8d18DECBa5798827539Ae99",
                                    "A_TOKEN": "0x38d693cE1dF5AaDF7bC62595A37D667aD57922e5",
                                    "S_TOKEN": "0x8a9FdE6925a839F6B1932d16B36aC026F8d3FbdB",
                                    "V_TOKEN": "0x5D557B07776D12967914379C71a1310e917C7555",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x73366Fe0AA0Ded304479862808e02506FE556a98",
                                    "STATA_TOKEN": "0x02E26888Ed3240BB38f26A2adF96Af9B52b167ea",
                                    "logoURI": "https://app.aave.com/icons/tokens/eurs.svg",
                                    "symbol": "EURS"
                                },
                                "jEUR": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4e3Decbb3645551B8A19f0eA1678079FCB33fB4c",
                                    "A_TOKEN": "0x6533afac2E7BCCB20dca161449A13A32D391fb00",
                                    "S_TOKEN": "0x6B4b37618D85Db2a7b469983C888040F7F05Ea3D",
                                    "V_TOKEN": "0x44705f578135cC5d703b4c9c122528C73Eb87145",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x73366Fe0AA0Ded304479862808e02506FE556a98",
                                    "STATA_TOKEN": "0xD992DaC78Ef3F34614E6a7d325b7b6A320FC0AB5",
                                    "logoURI": "https://app.aave.com/icons/tokens/jeur.svg",
                                    "symbol": "jEUR"
                                },
                                "EURA": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xE0B52e49357Fd4DAf2c15e02058DCE6BC0057db4",
                                    "A_TOKEN": "0x8437d7C167dFB82ED4Cb79CD44B7a32A1dd95c77",
                                    "S_TOKEN": "0x40B4BAEcc69B882e8804f9286b12228C27F8c9BF",
                                    "V_TOKEN": "0x3ca5FA07689F266e907439aFd1fBB59c44fe12f6",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x73366Fe0AA0Ded304479862808e02506FE556a98",
                                    "STATA_TOKEN": "0xd3eb8796Ed36f58E03B7b4b5AD417FA74931d2c4",
                                    "logoURI": "https://app.aave.com/icons/tokens/eura.svg",
                                    "symbol": "EURA"
                                },
                                "miMATIC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xa3Fa99A148fA48D14Ed51d610c367C61876997F1",
                                    "A_TOKEN": "0xeBe517846d0F36eCEd99C735cbF6131e1fEB775D",
                                    "S_TOKEN": "0x687871030477bf974725232F764aa04318A8b9c8",
                                    "V_TOKEN": "0x18248226C16BF76c032817854E7C83a2113B4f06",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x4ae2Ab1af7e3b0092dbF3A4B20ec3de8fC834873",
                                    "STATA_TOKEN": "0x8486B49433cCed038b51d18Ae3772CDB7E31CA5e",
                                    "logoURI": "https://app.aave.com/icons/tokens/mimatic.svg",
                                    "symbol": "miMATIC"
                                },
                                "stMATIC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x3A58a54C066FdC0f2D55FC9C89F0415C92eBf3C4",
                                    "A_TOKEN": "0xEA1132120ddcDDA2F119e99Fa7A27a0d036F7Ac9",
                                    "S_TOKEN": "0x1fFD28689DA7d0148ff0fCB669e9f9f0Fc13a219",
                                    "V_TOKEN": "0x6b030Ff3FB9956B1B69f475B77aE0d3Cf2CC5aFa",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x6D02E35031C4D99ee3A6A2BA47FaD0cFE355cA8f",
                                    "STATA_TOKEN": "0x867A180B7060fDC27610dC9096E93534F638A315",
                                    "logoURI": "https://app.aave.com/icons/tokens/stmatic.svg",
                                    "symbol": "stMATIC"
                                },
                                "MaticX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xfa68FB4628DFF1028CFEc22b4162FCcd0d45efb6",
                                    "A_TOKEN": "0x80cA0d8C38d2e2BcbaB66aA1648Bd1C7160500FE",
                                    "S_TOKEN": "0x62fC96b27a510cF4977B59FF952Dc32378Cc221d",
                                    "V_TOKEN": "0xB5b46F918C2923fC7f26DB76e8a6A6e9C4347Cf9",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xB0A72A5e454890e9715e059e8df8582a6B383DE3",
                                    "STATA_TOKEN": "0xbcDd5709641Af4BE99b1470A2B3A5203539132Ec",
                                    "logoURI": "https://app.aave.com/icons/tokens/maticx.svg",
                                    "symbol": "MaticX"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x03b54A6e9a984069379fae1a4fC4dBAE93B3bCCD",
                                    "A_TOKEN": "0xf59036CAEBeA7dC4b86638DFA2E3C97dA9FcCd40",
                                    "S_TOKEN": "0x173e54325AE58B072985DbF232436961981EA000",
                                    "V_TOKEN": "0x77fA66882a8854d883101Fb8501BD3CaD347Fc32",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xBD96b5ABBC6048c28184b462167E487533F2e35E",
                                    "STATA_TOKEN": "0x5274453F4CD5dD7280011a1Cca3B9e1b78EC59A6",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "USDCn": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x3c499c542cEF5E3811e1192ce70d8cC03d5c3359",
                                    "A_TOKEN": "0xA4D94019934D8333Ef880ABFFbF2FDd611C762BD",
                                    "S_TOKEN": "0xc889e9f8370D14A428a9857205d99BFdB400b757",
                                    "V_TOKEN": "0xE701126012EC0290822eEA17B794454d1AF8b030",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x17E33D122FC34c7ad8FBd4a1995Dff9c8aE675eb",
                                    "STATA_TOKEN": "0x2dCa80061632f3F87c9cA28364d1d0c30cD79a19",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                }
                            }
                        },
                        "534352": {
                            "address": "0x11fCfe756c05AD438e312a7fd934381537D3cFfe",
                            "ASSETS": {
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5300000000000000000000000000000000000004",
                                    "A_TOKEN": "0xf301805bE1Df81102C957f6d4Ce29d2B8c056B2a",
                                    "S_TOKEN": "0x117d9cF336287F46DBE509a43925cFF115Aa563c",
                                    "V_TOKEN": "0xfD7344CeB1Df9Cf238EcD667f4A6F99c6Ef44a56",
                                    "INTEREST_RATE_STRATEGY": "0xEC93d0BBA1b1e635ba0Fff4786dB323db49D99F0",
                                    "ORACLE": "0x6bF14CB0A831078629D993FDeBcB182b21A8774C",
                                    "STATA_TOKEN": "0x6b9DfaC194fa78a1882680E2cE19194D006AeEfd",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x06eFdBFf2a14a7c8E15944D1F4A48F9F95F663A4",
                                    "A_TOKEN": "0x1D738a3436A8C49CefFbaB7fbF04B660fb528CbD",
                                    "S_TOKEN": "0x59F359aA263f7Ac09876E869AF1F75b558904ed4",
                                    "V_TOKEN": "0x3d2E209af5BFa79297C88D6b57F89d792F6E28EE",
                                    "INTEREST_RATE_STRATEGY": "0xEC93d0BBA1b1e635ba0Fff4786dB323db49D99F0",
                                    "ORACLE": "0x427Fd98dbD1DbC2D4e792350caBe7c9665F35bee",
                                    "STATA_TOKEN": "0x9fA123bC7E6b61cC8a9D893673a4C6E5392FF4A7",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf610A9dfB7C89644979b4A0f27063E9e7d7Cda32",
                                    "A_TOKEN": "0x5B1322eeb46240b02e20062b8F0F9908d525B09c",
                                    "S_TOKEN": "0x18e3f125ce85e8D65AD2bb4f6b5fff110772A078",
                                    "V_TOKEN": "0x8a035644322129800C3f747f54Db0F4d3c0A2877",
                                    "INTEREST_RATE_STRATEGY": "0xEC93d0BBA1b1e635ba0Fff4786dB323db49D99F0",
                                    "ORACLE": "0x4EdAbf45e78363b8Dcd763bBbd05665c6e24975C",
                                    "STATA_TOKEN": "0x6e368c4dBf083e18a29aE63FC06AF9deDb3242F0",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                }
                            }
                        }
                    }
                    }//if the token is ERC20 token use this contract list and function
                    }
                },
        ```

    - LENDING_WITHDRAW

        **Description:** Remove deposited tokens and accrued interest from lending protocols, supporting partial or full withdrawals with consideration for borrowed positions, collateral ratios, and withdrawal limits based on protocol liquidity

        **Keywords:** withdraw lending, remove collateral, withdraw deposit, lending withdrawal, withdraw supplied, remove deposit, withdraw tokens, take out collateral, lending remove, withdraw assets, remove supplied, withdraw cryptocurrency, lending withdrawal, take out deposit, remove tokens, withdraw supplied assets, lending remove funds, withdraw from pool, remove from lending, protocol withdrawal

        ```tsx
        {
                    "action": "LENDING_WITHDRAW",
                    "network": "1",
                    "inputs": [
                        {
                            "name": "asset",
                            "type": "string",
                            "default": ""
                        },
                        {
                            "name": "amount",
                            "type": "string",
                            "default": ""
                        }
                    ],
                    "outputs": [
                        {
                            "name": "success",
                            "type": "boolean"
                        }
                    ],
                    "protocol": {
                "name": "AAVE"
                    "withdrawETH":{
                    "functionName": "withdrawETH",
                    "contract": {
                        "42161": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0xecD4bd3121F9FD604ffaC631bF6d41ec12f1fafb"
                        },
                        "43114": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0x2DeC8BCE3471eD65B1bB558Fa28439D45bF446d0"
                        },
                        "8453": {
                            "pool": "0xA238Dd80C259a72e81d7e4664a9801593F98d1c5",
                            "address": "0x8be473dCfA93132658821E67CbEB684ec8Ea2E74"
                        },
                        "56": {
                            "pool": "0x6807dc923806fE8Fd134338EABCA509979a7e0cB",
                            "address": "0x326aB0868bD279382Be2DF5E228Cb8AF38649AB4"
                        },
                        "1": {
                            "pool": "0x87870Bca3F3fD6335C3F4ce8392D69350B4fA4E2",
                            "address": "0x893411580e590D62dDBca8a703d61Cc4A8c7b2b9"
                        },
                        "10": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0xe9E52021f4e11DEAD8661812A0A6c8627abA2a54"
                        },
                        "137": {
                            "pool": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "address": "0xC1E320966c485ebF2A0A2A6d3c0Dc860A156eB1B"
                        },
                        "534352": {
                            "pool": "0x11fCfe756c05AD438e312a7fd934381537D3cFfe",
                            "address": "0xFF75A4B698E3Ec95E608ac0f22A03B8368E05F5D"
                        }
                    }
                    }//if the token is native token use this contract list and function

                    "withdraw": {
                    "functionName": "withdraw",
                    "contract": {
                        "42161": {
                            "address": "0x794@a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xDA10009cBd5D07dd0CeCc66161FC93D7c9000da1",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x4a838a3Dac6633bB1fd932B6f356DecFCAf7803D",
                                    "STATA_TOKEN": "0xc91c5297d7E161aCC74b482aAfCc75B85cc0bfeD",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf97f4df75117a78c1A5a0DBb814Af92458539FB4",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x86E53CF1B870786351Da77A57575e79CB55812CB",
                                    "STATA_TOKEN": "0x27dE098EF2772386cBCf1a4c8BEb886368b7F9a9",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xDe25a88F87FEd9F8999fAbF6729dCB121893623C",
                                    "STATA_TOKEN": "0x0Bc9E52051f553E75550CA22C196bf132c52Cf0B",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC.e"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x2f2a2543B76A4166549F7aaB2e75Bef0aefC5B0f",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x6ce185860a4963106506C203335A2910413708e9",
                                    "STATA_TOKEN": "0x32B95Fbe04e5a51cF99FeeF4e57Cf7e3FC9c5A93",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x82aF49447D8a07e3bd95BD0d56f35241523fBab1",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x639Fe6ab55C921f74e7fac1ee960C0B6293ba612",
                                    "STATA_TOKEN": "0x352F3475716261dCC991Bd5F2aF973eB3D0F5878",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xFd086bC7CD5C481DCC9C85ebE478A1C0b69FCbb9",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x84dC1C52D7C340AA54B4e8799FBB31C3D28E67aD",
                                    "STATA_TOKEN": "0xb165a74407fE1e519d6bCbDeC1Ed3202B35a4140",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xba5DdD1f9d7F570dc94a51479a000E3BCE967196",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xaD1d5344AaDE45F43E596773Bcc4c423EAbdD034",
                                    "STATA_TOKEN": "0x1C0c8EcED17aE093b3C1a1a8fFeBE2E9513a9346",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "EURS": {
                                    "decimals": 2,
                                    "UNDERLYING": "0xD22a58f79e9481D1a88e00c343885A588b34b68B",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xA14d53bC1F1c0F31B4aA3BD109344E5009051a84",
                                    "STATA_TOKEN": "0x9a40747BE51185A416B181789B671E78a8d045dD",
                                    "logoURI": "https://app.aave.com/icons/tokens/eurs.svg",
                                    "symbol": "EURS"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5979D7b546E38E414F7E9822514be443A4800529",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x87fE1503beFBF98C35c7526B0c488d950F822C0F",
                                    "STATA_TOKEN": "0x7775d4Ae4Dbb79a624fB96AAcDB8Ca74F671c0DF",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "MAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x3F56e0c36d275367b8C502090EDF38289b3dEa0d",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x7a7cE08a1057723CCEDeA2462407427Ae33FFEb2",
                                    "STATA_TOKEN": "0xB4a0a2692D82301703B27082Cda45B083F68CAcE",
                                    "logoURI": "https://app.aave.com/icons/tokens/mai.svg",
                                    "symbol": "MAI"
                                },
                                "rETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xEC70Dcb4A1EFa46b8F2D97C310C9c4790ba5ffA8",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x256f33FC0110B1297f78f48524631D30B752480D",
                                    "STATA_TOKEN": "0x68235105d6d33A19369D24b746cb7481FB2b34fd",
                                    "logoURI": "https://app.aave.com/icons/tokens/reth.svg",
                                    "symbol": "rETH"
                                },
                                "LUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x93b346b6BC2548dA6A1E7d98E9a421B42541425b",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x341B110bDF665A20F0D5f84A92FcAF5EbeEBC629",
                                    "STATA_TOKEN": "0xDbB6314b5b07E63B7101844c0346309B79f8C20A",
                                    "logoURI": "https://app.aave.com/icons/tokens/lusd.svg",
                                    "symbol": "LUSD"
                                },
                                "USDCn": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xaf88d065e77c8cC2239327C5EDb3A432268e5831",
                                    "A_TOKEN": "0x724dc807b04555b71ed48a6896b6F41593b8C637",
                                    "S_TOKEN": "0xDC1fad70953Bb3918592b6fCc374fe05F5811B6a",
                                    "V_TOKEN": "0xf611aEb5013fD2c0511c9CD55c7dc5C1140741A6",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xDe25a88F87FEd9F8999fAbF6729dCB121893623C",
                                    "STATA_TOKEN": "0x7CFaDFD5645B50bE87d546f42699d863648251ad",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "FRAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x17FC002b466eEc40DaE837Fc4bE5c67993ddBd6F",
                                    "A_TOKEN": "0x38d693cE1dF5AaDF7bC62595A37D667aD57922e5",
                                    "S_TOKEN": "0x8a9FdE6925a839F6B1932d16B36aC026F8d3FbdB",
                                    "V_TOKEN": "0x5D557B07776D12967914379C71a1310e917C7555",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x06919EB75Bd6BA817D38CC70C1CA588ac7a01C10",
                                    "STATA_TOKEN": "0x89AEc2023f89E26Dbb7eaa7a98fe3996f9d112A8",
                                    "logoURI": "https://app.aave.com/icons/tokens/frax.svg",
                                    "symbol": "FRAX"
                                },
                                "ARB": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x912CE59144191C1204E64559FE8253a0e49E6548",
                                    "A_TOKEN": "0x6533afac2E7BCCB20dca161449A13A32D391fb00",
                                    "S_TOKEN": "0x6B4b37618D85Db2a7b469983C888040F7F05Ea3D",
                                    "V_TOKEN": "0x44705f578135cC5d703b4c9c122528C73Eb87145",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xb2A824043730FE05F3DA2efaFa1CBbe83fa548D6",
                                    "STATA_TOKEN": "0x9b5637d7952BC9fa2D693aAE51f3103760Bf2693",
                                    "logoURI": "https://app.aave.com/icons/tokens/arb.svg",
                                    "symbol": "ARB"
                                },
                                "weETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x35751007a407ca6FEFfE80b3cB397736D2cf4dbe",
                                    "A_TOKEN": "0x8437d7C167dFB82ED4Cb79CD44B7a32A1dd95c77",
                                    "S_TOKEN": "0x40B4BAEcc69B882e8804f9286b12228C27F8c9BF",
                                    "V_TOKEN": "0x3ca5FA07689F266e907439aFd1fBB59c44fe12f6",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x517276B5972C4Db7E88B9F76Ee500E888a2D73C3",
                                    "logoURI": "https://app.aave.com/icons/tokens/weeth.svg",
                                    "symbol": "weETH"
                                },
                                "GHO": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7dfF72693f6A4149b17e7C6314655f6A9F7c8B33",
                                    "A_TOKEN": "0xeBe517846d0F36eCEd99C735cbF6131e1fEB775D",
                                    "S_TOKEN": "0x687871030477bf974725232F764aa04318A8b9c8",
                                    "V_TOKEN": "0x18248226C16BF76c032817854E7C83a2113B4f06",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xB05984aD83C20b3ADE7bf97a9a0Cb539DDE28DBb",
                                    "logoURI": "https://app.aave.com/icons/tokens/gho.svg",
                                    "symbol": "GHO"
                                }
                            }
                        },
                        "43114": {
                            "address": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAIe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xd586E7F844cEa2F87f50152665BCbc2C279D8d70",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xf82da795727633aFA9BB0f1B08A87c0F6A38723f",
                                    "STATA_TOKEN": "0x02F3f6c8A432C1e49f3359d7d36887C25d8A5888",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI.e"
                                },
                                "LINKe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5947BB275c521040051D82396192181b413227A3",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x49ccd9ca821EfEab2b98c60dC60F518E765EDe9a",
                                    "STATA_TOKEN": "0x8B773Ab77Dff01985D438961dBCE58382a70cA52",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK.e"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xB97EF9Ef8734C71904D8002F8b6Bc66Dd9c48a6E",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xD8277249e871BE9A402fa286C2C5ec16046dC512",
                                    "STATA_TOKEN": "0xC509aB7bB4eDbF193b82264D499a7Fc526Cd01F4",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "WBTCe": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x50b7545627a5162F82A992c33b87aDc75187B218",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x2779D32d5166BAaa2B2b658333bA7e6Ec0C65743",
                                    "STATA_TOKEN": "0xE3C0f42EAF1a4BFe37CbA105e5463564BA7730aE",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC.e"
                                },
                                "WETHe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x49D5c2BdFfac6CE2BFdB6640F4F80f226bc10bAB",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x976B3D034E162d8bD72D6b9C989d545b839003b0",
                                    "STATA_TOKEN": "0xf8E24175D01653fd6AA203C2C17B1e4Dd1CA2731",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH.e"
                                },
                                "USDt": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x9702230A8Ea53601f5cD2dc00fDBc13d4dF4A8c7",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x39185f2236A6022b682e8BB93C040d125DA093CF",
                                    "STATA_TOKEN": "0x5525Ee69BC1e354B356864187De486fab5AD67d7",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDt"
                                },
                                "AAVEe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x63a72806098Bd3D9520cC43356dD78afe5D386D9",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x3CA13391E9fb38a75330fb28f8cc2eB3D9ceceED",
                                    "STATA_TOKEN": "0xac0746AfD13DEbe2a43a6c8745Fb83Fd2A2909cA",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE.e"
                                },
                                "WAVAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xB31f66AA3C1e785363F0875A1B74E27b85FD66c7",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x0A77230d17318075983913bC2145DB16C7366156",
                                    "STATA_TOKEN": "0x6A02C7a974F1F13A67980C80F774eC1d2eD8f98d",
                                    "logoURI": "https://app.aave.com/icons/tokens/wavax.svg",
                                    "symbol": "WAVAX"
                                },
                                "sAVAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x2b2C81e08f1Af8835a78Bb2A90AE924ACE0eA4bE",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xB2B332f27e4B7305649a228C31Ed9858c5a6bAD9",
                                    "STATA_TOKEN": "0x4F059cA8a2a5BF8895Ee731f2E901cCB769FB95f",
                                    "logoURI": "https://app.aave.com/icons/tokens/savax.svg",
                                    "symbol": "sAVAX"
                                },
                                "FRAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD24C2Ad096400B6FBcd2ad8B24E7acBc21A1da64",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x6208576378D06ce69A27987b7A524A9B15d499a4",
                                    "STATA_TOKEN": "0xA3c2ffE702F4cD265B2249AB5f84Fab81FFf6c73",
                                    "logoURI": "https://app.aave.com/icons/tokens/frax.svg",
                                    "symbol": "FRAX"
                                },
                                "MAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5c49b268c9841AFF1Cc3B0a418ff5c3442eE3F3b",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0xCcC55Db26B78a19Dba1beE0066F9c1665575439A",
                                    "STATA_TOKEN": "0x08cC59E51BB0Bc322B4D251f7262dB864d6150ce",
                                    "logoURI": "https://app.aave.com/icons/tokens/mai.svg",
                                    "symbol": "MAI"
                                },
                                "BTCb": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x152b9d0FdC40C096757F570A51E494bd4b943E50",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0x43dD6f474e436348db037BAeA24eD02E68c475bE",
                                    "ORACLE": "0x2779D32d5166BAaa2B2b658333bA7e6Ec0C65743",
                                    "STATA_TOKEN": "0x34d768cc830c32DcD743321c09A2A702651bF9a2",
                                    "logoURI": "https://app.aave.com/icons/tokens/btc.svg",
                                    "symbol": "BTC.b"
                                }
                            }
                        },
                        "8453": {
                            "address": "0xA238Dd80C259a72e81d7e4664a9801593F98d1c5",
                            "ASSETS": {
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4200000000000000000000000000000000000006",
                                    "A_TOKEN": "0xD4a0e0b9149BCee3C920d2E00b5dE09138fd8bb7",
                                    "S_TOKEN": "0xaED3b56FeA82E809665f02AcBcDEc0816c75f4d9",
                                    "V_TOKEN": "0x24e6e0795b3c7c71D965fCc4f371803d1c1DcA1E",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x71041dddad3595F9CEd3DcCFBe3D1F4b0a16Bb70",
                                    "STATA_TOKEN": "0x468973e3264F2aEba0417A8f2cD0Ec397E738898",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "cbETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x2Ae3F1Ec7F1F5012CFEab0185bfc7aa3cf0DEc22",
                                    "A_TOKEN": "0xcf3D55c10DB69f28fD1A75Bd73f3D8A2d9c595ad",
                                    "S_TOKEN": "0xa9dF5c62d16d3f496673F4d736852017b086eCA0",
                                    "V_TOKEN": "0x1DabC36f19909425f654777249815c073E8Fd79F",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x8e11Ad4531826ff47BD8157a2c705F5422Da6A61",
                                    "STATA_TOKEN": "0x16A004065dfb11276DcB29Dc03fb8A85f9A43C6e",
                                    "logoURI": "https://app.aave.com/icons/tokens/cbeth.svg",
                                    "symbol": "cbETH"
                                },
                                "USDbC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xd9aAEc86B65D86f6A7B5B1b0c42FFA531710b6CA",
                                    "A_TOKEN": "0x0a1d576f3eFeF75b330424287a95A366e8281D54",
                                    "S_TOKEN": "0xBBaDd47fbaFa9dE717FE203e4707DEB893C64654",
                                    "V_TOKEN": "0x7376b2F323dC56fCd4C191B34163ac8a84702DAB",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x978D8878b53Fbe40dab7D4AB47b97AB622FFeF9f",
                                    "STATA_TOKEN": "0x6fCe2756794128B1771324caA860965801DCbCdB",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdbc.svg",
                                    "symbol": "USDbC"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xc1CBa3fCea344f92D9239c08C0568f6F2F0ee452",
                                    "A_TOKEN": "0x99CBC45ea5bb7eF3a5BC08FB1B7E56bB2442Ef0D",
                                    "S_TOKEN": "0xfe742Fa2a84294E8316F05b17c05090Fc68B5105",
                                    "V_TOKEN": "0x41A7C3f5904ad176dACbb1D99101F59ef0811DC1",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x56038D3998C42db18ba3B821bD1EbaB9B678e657",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913",
                                    "A_TOKEN": "0x4e65fE4DbA92790696d040ac24Aa414708F5c0AB",
                                    "S_TOKEN": "0x03506214379aA86ad1176af71c260278cfa10B38",
                                    "V_TOKEN": "0x59dca05b6c26dbd64b5381374aAaC5CD05644C28",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0x978D8878b53Fbe40dab7D4AB47b97AB622FFeF9f",
                                    "STATA_TOKEN": "0x4EA71A20e655794051D1eE8b6e4A3269B13ccaCc",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "weETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x04C0599Ae5A44757c0af6F9eC3b93da8976c150A",
                                    "A_TOKEN": "0x7C307e128efA31F540F2E2d976C995E0B65F51F6",
                                    "S_TOKEN": "0xCBEdA45432D5325585ACAD29244f113C237B6Cf0",
                                    "V_TOKEN": "0x8D2e3F1f4b38AA9f1ceD22ac06019c7561B03901",
                                    "INTEREST_RATE_STRATEGY": "0x46Da028a47Ed58026aCbFbE91eeA51CcB062134E",
                                    "ORACLE": "0xFc4d1d7a8FD1E6719e361e16044b460737F12C44",
                                    "logoURI": "https://app.aave.com/icons/tokens/weeth.svg",
                                    "symbol": "weETH"
                                }
                            }
                        },
                        "56": {
                            "address": "0x326aB0868bD279382Be2DF5E228Cb8AF38649AB4",
                            "ASSETS": {
                                "Cake": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82",
                                    "A_TOKEN": "0x4199CC1F5ed0d796563d7CcB2e036253E2C18281",
                                    "S_TOKEN": "0x57e95511de39890D3e782df4b19F0D97A05DF64A",
                                    "V_TOKEN": "0xE20dBC7119c635B1B51462f844861258770e0699",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0xB6064eD41d4f67e353768aA239cA86f4F73665a1",
                                    "STATA_TOKEN": "0x3854354CE3681da1D7F550073061E92a4a7d1B27",
                                    "logoURI": "https://app.aave.com/icons/tokens/cake.svg",
                                    "symbol": "Cake"
                                },
                                "WBNB": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xbb4CdB9CBd36B01bD1cBaEBF2De08d9173bc095c",
                                    "A_TOKEN": "0x9B00a09492a626678E5A3009982191586C444Df9",
                                    "S_TOKEN": "0x5cc46d2b1103aB23CFD63eF8631480bbf4eB40FE",
                                    "V_TOKEN": "0x0E76414d433ddfe8004d2A7505d218874875a996",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x0567F2323251f0Aab15c8dFb1967E4e8A7D42aeE",
                                    "STATA_TOKEN": "0x436baCb4C66583de4Cb16e13a1A0D9A3075DE425",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbnb.svg",
                                    "symbol": "WBNB"
                                },
                                "BTCB": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7130d2A12B9BCbFAe4f2634d864A1Ee1Ce3Ead9c",
                                    "A_TOKEN": "0x56a7ddc4e848EbF43845854205ad71D5D5F72d3D",
                                    "S_TOKEN": "0x9Ef6D76740713C674A6e4f38B863E62D10965053",
                                    "V_TOKEN": "0x7b1E82F4f542fbB25D64c5523Fe3e44aBe4F2702",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x264990fbd0A4796A3E3d8E37C4d5F87a3aCa5Ebf",
                                    "STATA_TOKEN": "0x1F66b530084079d35478A069d9c4424F9c9C320c",
                                    "logoURI": "https://app.aave.com/icons/tokens/btcb.svg",
                                    "symbol": "BTCB"
                                },
                                "ETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x2170Ed0880ac9A755fd29B2688956BD959F933F8",
                                    "A_TOKEN": "0x2E94171493fAbE316b6205f1585779C887771E2F",
                                    "S_TOKEN": "0xa8327EE1858E06983af6690d24e77774807109d4",
                                    "V_TOKEN": "0x8FDea7891b4D6dbdc746309245B316aF691A636C",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x9ef1B8c0E4F7dc8bF5719Ea496883DC6401d5b2e",
                                    "STATA_TOKEN": "0x52077433fB7053D747E2846aD0C18ff5015C368E",
                                    "logoURI": "https://app.aave.com/icons/tokens/eth.svg",
                                    "symbol": "ETH"
                                },
                                "USDC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x8AC76a51cc950d9822D68b83fE1Ad97B32Cd580d",
                                    "A_TOKEN": "0x00901a076785e0906d1028c7d6372d247bec7d61",
                                    "S_TOKEN": "0xCcC260D9778F900eAd566Fa2E1D622E667677653",
                                    "V_TOKEN": "0xcDBBEd5606d9c5C98eEedd67933991dC17F0c68d",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0xaFcFF74AE956f4c23c27Db49659D4a7F350415C1",
                                    "STATA_TOKEN": "0x3906cDdfb781f02B21f21BD81ed7Fd8DC37075E1",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "USDT": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x55d398326f99059fF775485246999027B3197955",
                                    "A_TOKEN": "0xa9251ca9DE909CB71783723713B21E4233fbf1B1",
                                    "S_TOKEN": "0xB735D922a36d4337f561CE433594727e1bc8bD01",
                                    "V_TOKEN": "0xF8bb2Be50647447Fb355e3a77b81be4db64107cd",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x0F682319Ed4A240b7a2599A48C965049515D9bC3",
                                    "STATA_TOKEN": "0x0471D185cc7Be61E154277cAB2396cD397663da6",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "FDUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xc5f0f7b66764F6ec8C8Dff7BA683102295E16409",
                                    "A_TOKEN": "0x75bd1A659bdC62e4C313950d44A2416faB43E785",
                                    "S_TOKEN": "0x5543d347bfae77A5FF913e589aB6D6ad520f1C73",
                                    "V_TOKEN": "0xE628B8a123e6037f1542e662B9F55141a16945C8",
                                    "INTEREST_RATE_STRATEGY": "0x51D86C833fC4F300196F028FEaC899a94eb82eFb",
                                    "ORACLE": "0x60a117Fa5bAbee4d645884fB11E413Da4F893b6D",
                                    "STATA_TOKEN": "0x4d074aAa0821073dA827f7bf6a02cF905b394ed0",
                                    "logoURI": "https://app.aave.com/icons/tokens/fdusd.svg",
                                    "symbol": "FDUSD"
                                }
                            }
                        },
                        "1": {
                            "address": "0x87870Bca3F3fD6335C3F4ce8392D69350B4fA4E2",
                            "ASSETS": {
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2",
                                    "A_TOKEN": "0x4d5F47FA6A74757f35C14fD3a6Ef8E3C9BC514E8",
                                    "S_TOKEN": "0x102633152313C81cD80419b6EcF66d14Ad68949A",
                                    "V_TOKEN": "0xeA51d7853EEFb32b6ee06b1C12E6dcCA88Be0fFE",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x5f4eC3Df9cbd43714FE2740f5E3616155c5b8419",
                                    "STATA_TOKEN": "0x252231882FB38481497f3C767469106297c8d93b",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7f39C581F595B53c5cb19bD0b3f8dA6c935E2Ca0",
                                    "A_TOKEN": "0x0B925eD163218f6662a35e0f0371Ac234f9E9371",
                                    "S_TOKEN": "0x39739943199c0fBFe9E5f1B5B160cd73a64CB85D",
                                    "V_TOKEN": "0xC96113eED8cAB59cD8A66813bCB0cEb29F06D2e4",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xB4aB0c94159bc2d8C133946E7241368fc2F2a010",
                                    "STATA_TOKEN": "0x322AA5F5Be95644d6c36544B6c5061F072D16DF5",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x2260FAC5E5542a773Aa44fBCfeDf7C193bc2C599",
                                    "A_TOKEN": "0x5Ee5bf7ae06D1Be5997A1A72006FE6C607eC6DE8",
                                    "S_TOKEN": "0xA1773F1ccF6DB192Ad8FE826D15fe1d328B03284",
                                    "V_TOKEN": "0x40aAbEf1aa8f0eEc637E0E7d92fbfFB2F26A8b7B",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x230E0321Cf38F09e247e50Afc7801EA2351fe56F",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48",
                                    "A_TOKEN": "0x98C23E9d8f34FEFb1B7BD6a91B7FF122F4e16F5c",
                                    "S_TOKEN": "0xB0fe3D292f4bd50De902Ba5bDF120Ad66E9d7a39",
                                    "V_TOKEN": "0x72E95b8931767C79bA4EeE721354d6E99a61D004",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x736bF902680e68989886e9807CD7Db4B3E015d3C",
                                    "STATA_TOKEN": "0x73edDFa87C71ADdC275c2b9890f5c3a8480bC9E6",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x6B175474E89094C44Da98b954EedeAC495271d0F",
                                    "A_TOKEN": "0x018008bfb33d285247A21d44E50697654f754e63",
                                    "S_TOKEN": "0x413AdaC9E2Ef8683ADf5DDAEce8f19613d60D1bb",
                                    "V_TOKEN": "0xcF8d0c70c850859266f5C338b38F9D663181C314",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xaEb897E1Dc6BbdceD3B9D551C71a8cf172F27AC4",
                                    "STATA_TOKEN": "0xaf270C38fF895EA3f95Ed488CEACe2386F038249",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x514910771AF9Ca656af840dff83E8264EcF986CA",
                                    "A_TOKEN": "0x5E8C8A7243651DB1384C0dDfDbE39761E8e7E51a",
                                    "S_TOKEN": "0x63B1129ca97D2b9F97f45670787Ac12a9dF1110a",
                                    "V_TOKEN": "0x4228F8895C7dDA20227F6a5c6751b8Ebf19a6ba8",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x2c1d072e956AFFC0D435Cb7AC38EF18d24d9127c",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7Fc66500c84A76Ad7e9c93437bFc5Ac33E2DDaE9",
                                    "A_TOKEN": "0xA700b4eB416Be35b2911fd5Dee80678ff64fF6C9",
                                    "S_TOKEN": "0x268497bF083388B1504270d0E717222d3A87D6F2",
                                    "V_TOKEN": "0xBae535520Abd9f8C85E58929e0006A2c8B372F74",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x547a514d5e3769680Ce22B2361c10Ea13619e8a9",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "cbETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xBe9895146f7AF43049ca1c1AE358B0541Ea49704",
                                    "A_TOKEN": "0x977b6fc5dE62598B08C85AC8Cf2b745874E8b78c",
                                    "S_TOKEN": "0x82bE6012cea6D147B968eBAea5ceEcF6A5b4F493",
                                    "V_TOKEN": "0x0c91bcA95b5FE69164cE583A2ec9429A569798Ed",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x6243d2F41b4ec944F731f647589E28d9745a2674",
                                    "logoURI": "https://app.aave.com/icons/tokens/cbeth.svg",
                                    "symbol": "cbETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xdAC17F958D2ee523a2206206994597C13D831ec7",
                                    "A_TOKEN": "0x23878914EFE38d27C4D67Ab83ed1b93A74D4086a",
                                    "S_TOKEN": "0x822Fa72Df1F229C3900f5AD6C3Fa2C424D691622",
                                    "V_TOKEN": "0x6df1C1E379bC5a00a7b4C6e67A203333772f45A8",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xC26D4a1c46d884cfF6dE9800B6aE7A8Cf48B4Ff8",
                                    "STATA_TOKEN": "0x862c57d48becB45583AEbA3f489696D22466Ca1b",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "rETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xae78736Cd615f374D3085123A210448E74Fc6393",
                                    "A_TOKEN": "0xCc9EE9483f662091a1de4795249E24aC0aC2630f",
                                    "S_TOKEN": "0x1d1906f909CAe494c7441604DAfDDDbD0485A925",
                                    "V_TOKEN": "0xae8593DD575FE29A9745056aA91C4b746eee62C8",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x5AE8365D0a30D67145f0c55A08760C250559dB64",
                                    "logoURI": "https://app.aave.com/icons/tokens/reth.svg",
                                    "symbol": "rETH"
                                },
                                "LUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5f98805A4E8be255a32880FDeC7F6728C6568bA0",
                                    "A_TOKEN": "0x3Fe6a295459FAe07DF8A0ceCC36F37160FE86AA9",
                                    "S_TOKEN": "0x37A6B708FDB1483C231961b9a7F145261E815fc3",
                                    "V_TOKEN": "0x33652e48e4B74D18520f11BfE58Edd2ED2cEc5A2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x9eCdfaCca946614cc32aF63F3DBe50959244F3af",
                                    "STATA_TOKEN": "0xDBf5E36569798D1E39eE9d7B1c61A7409a74F23A",
                                    "logoURI": "https://app.aave.com/icons/tokens/lusd.svg",
                                    "symbol": "LUSD"
                                },
                                "CRV": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD533a949740bb3306d119CC777fa900bA034cd52",
                                    "A_TOKEN": "0x7B95Ec873268a6BFC6427e7a28e396Db9D0ebc65",
                                    "S_TOKEN": "0x90D9CD005E553111EB8C9c31Abe9706a186b6048",
                                    "V_TOKEN": "0x1b7D3F4b3c032a5AE656e30eeA4e8E1Ba376068F",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xCd627aA160A6fA45Eb793D19Ef54f5062F20f33f",
                                    "logoURI": "https://app.aave.com/icons/tokens/crv.svg",
                                    "symbol": "CRV"
                                },
                                "MKR": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9f8F72aA9304c8B593d555F12eF6589cC3A579A2",
                                    "A_TOKEN": "0x8A458A9dc9048e005d22849F470891b840296619",
                                    "S_TOKEN": "0x0496372BE7e426D28E89DEBF01f19F014d5938bE",
                                    "V_TOKEN": "0x6Efc73E54E41b27d2134fF9f98F15550f30DF9B1",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xec1D1B3b0443256cc3860e24a46F108e699484Aa",
                                    "logoURI": "https://app.aave.com/icons/tokens/mkr.svg",
                                    "symbol": "MKR"
                                },
                                "SNX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xC011a73ee8576Fb46F5E1c5751cA3B9Fe0af2a6F",
                                    "A_TOKEN": "0xC7B4c17861357B8ABB91F25581E7263E08DCB59c",
                                    "S_TOKEN": "0x478E1ec1A2BeEd94c1407c951E4B9e22d53b2501",
                                    "V_TOKEN": "0x8d0de040e8aAd872eC3c33A3776dE9152D3c34ca",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xDC3EA94CD0AC27d9A86C180091e7f78C683d3699",
                                    "logoURI": "https://app.aave.com/icons/tokens/snx.svg",
                                    "symbol": "SNX"
                                },
                                "BAL": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xba100000625a3754423978a60c9317c58a424e3D",
                                    "A_TOKEN": "0x2516E7B3F76294e03C42AA4c5b5b4DCE9C436fB8",
                                    "S_TOKEN": "0xB368d45aaAa07ee2c6275Cb320D140b22dE43CDD",
                                    "V_TOKEN": "0x3D3efceb4Ff0966D34d9545D3A2fa2dcdBf451f2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xdF2917806E30300537aEB49A7663062F4d1F2b5F",
                                    "logoURI": "https://app.aave.com/icons/tokens/bal.svg",
                                    "symbol": "BAL"
                                },
                                "UNI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x1f9840a85d5aF5bf1D1762F925BDADdC4201F984",
                                    "A_TOKEN": "0xF6D2224916DDFbbab6e6bd0D1B7034f4Ae0CaB18",
                                    "S_TOKEN": "0x2FEc76324A0463c46f32e74A86D1cf94C02158DC",
                                    "V_TOKEN": "0xF64178Ebd2E2719F2B1233bCb5Ef6DB4bCc4d09a",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x553303d460EE0afB37EdFf9bE42922D8FF63220e",
                                    "logoURI": "https://app.aave.com/icons/tokens/uni.svg",
                                    "symbol": "UNI"
                                },
                                "LDO": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5A98FcBEA516Cf06857215779Fd812CA3beF1B32",
                                    "A_TOKEN": "0x9A44fd41566876A39655f74971a3A6eA0a17a454",
                                    "S_TOKEN": "0xa0a5bF5781Aeb548db9d4226363B9e89287C5FD2",
                                    "V_TOKEN": "0xc30808705C01289A3D306ca9CAB081Ba9114eC82",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xb01e6C9af83879B8e06a092f0DD94309c0D497E4",
                                    "logoURI": "https://app.aave.com/icons/tokens/ldo.svg",
                                    "symbol": "LDO"
                                },
                                "ENS": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xC18360217D8F7Ab5e7c516566761Ea12Ce7F9D72",
                                    "A_TOKEN": "0x545bD6c032eFdde65A377A6719DEF2796C8E0f2e",
                                    "S_TOKEN": "0x7617d02E311CdE347A0cb45BB7DF2926BBaf5347",
                                    "V_TOKEN": "0xd180D7fdD4092f07428eFE801E17BC03576b3192",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x5C00128d4d1c2F4f652C267d7bcdD7aC99C16E16",
                                    "logoURI": "https://app.aave.com/icons/tokens/ens.svg",
                                    "symbol": "ENS"
                                },
                                "ONE_INCH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x111111111117dC0aa78b770fA6A738034120C302",
                                    "A_TOKEN": "0x71Aef7b30728b9BB371578f36c5A1f1502a5723e",
                                    "S_TOKEN": "0x4b62bFAff61AB3985798e5202D2d167F567D0BCD",
                                    "V_TOKEN": "0xA38fCa8c6Bf9BdA52E76EB78f08CaA3BE7c5A970",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xc929ad75B72593967DE83E7F7Cda0493458261D9",
                                    "logoURI": "https://app.aave.com/icons/tokens/1inch.svg",
                                    "symbol": "1INCH"
                                },
                                "FRAX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x853d955aCEf822Db058eb8505911ED77F175b99e",
                                    "A_TOKEN": "0xd4e245848d6E1220DBE62e155d89fa327E43CB06",
                                    "S_TOKEN": "0x219640546c0DFDDCb9ab3bcdA89B324e0a376367",
                                    "V_TOKEN": "0x88B8358F5BC87c2D7E116cCA5b65A9eEb2c5EA3F",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x45D270263BBee500CF8adcf2AbC0aC227097b036",
                                    "STATA_TOKEN": "0xEE66abD4D0f9908A48E08AE354B0f425De3e237E",
                                    "logoURI": "https://app.aave.com/icons/tokens/frax.svg",
                                    "symbol": "FRAX"
                                },
                                "GHO": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x40D16FC0246aD3160Ccc09B8D0D3A2cD28aE6C2f",
                                    "A_TOKEN": "0x00907f9921424583e7ffBfEdf84F92B7B2Be4977",
                                    "S_TOKEN": "0x3f3DF7266dA30102344A813F1a3D07f5F041B5AC",
                                    "V_TOKEN": "0x786dBff3f1292ae8F92ea68Cf93c30b34B1ed04B",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xD110cac5d8682A3b045D5524a9903E031d70FCCd",
                                    "logoURI": "https://app.aave.com/icons/tokens/gho.svg",
                                    "symbol": "GHO"
                                },
                                "RPL": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD33526068D116cE69F19A9ee46F0bd304F21A51f",
                                    "A_TOKEN": "0xB76CF92076adBF1D9C39294FA8e7A67579FDe357",
                                    "S_TOKEN": "0x41e330fd8F7eA31E2e8F02cC0C9392D1403597B4",
                                    "V_TOKEN": "0x8988ECA19D502fd8b9CCd03fA3bD20a6f599bc2A",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x4E155eD98aFE9034b7A5962f6C84c86d869daA9d",
                                    "logoURI": "https://app.aave.com/icons/tokens/rpl.svg",
                                    "symbol": "RPL"
                                },
                                "sDAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x83F20F44975D03b1b09e64809B757c47f942BEeA",
                                    "A_TOKEN": "0x4C612E3B15b96Ff9A6faED838F8d07d479a8dD4c",
                                    "S_TOKEN": "0x48Bc45f084988bC01933EA93EeFfEBC0416534f6",
                                    "V_TOKEN": "0x8Db9D35e117d8b93C6Ca9b644b25BaD5d9908141",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x29081f7aB5a644716EfcDC10D5c926c5fEe9F72B",
                                    "logoURI": "https://app.aave.com/icons/tokens/sdai.svg",
                                    "symbol": "sDAI"
                                },
                                "STG": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xAf5191B0De278C7286d6C7CC6ab6BB8A73bA2Cd6",
                                    "A_TOKEN": "0x1bA9843bD4327c6c77011406dE5fA8749F7E3479",
                                    "S_TOKEN": "0xc3115D0660b93AeF10F298886ae22E3Dd477E482",
                                    "V_TOKEN": "0x655568bDd6168325EC7e58Bf39b21A856F906Dc2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x7A9f34a0Aa917D438e9b6E630067062B7F8f6f3d",
                                    "logoURI": "https://app.aave.com/icons/tokens/stg.svg",
                                    "symbol": "STG"
                                },
                                "KNC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xdeFA4e8a7bcBA345F687a2f1456F5Edd9CE97202",
                                    "A_TOKEN": "0x5b502e3796385E1e9755d7043B9C945C3aCCeC9C",
                                    "S_TOKEN": "0xdfEE0C9eA1309cB9611F33972E72a72166fcF548",
                                    "V_TOKEN": "0x253127Ffc04981cEA8932F406710661c2f2c3fD2",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xf8fF43E991A81e6eC886a3D281A2C6cC19aE70Fc",
                                    "logoURI": "https://app.aave.com/icons/tokens/knc.svg",
                                    "symbol": "KNC"
                                },
                                "FXS": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x3432B6A60D23Ca0dFCa7761B7ab56459D9C964D0",
                                    "A_TOKEN": "0x82F9c5ad306BBa1AD0De49bB5FA6F01bf61085ef",
                                    "S_TOKEN": "0x61dFd349140C239d3B61fEe203Efc811b518a317",
                                    "V_TOKEN": "0x68e9f0aD4e6f8F5DB70F6923d4d6d5b225B83b16",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x6Ebc52C8C1089be9eB3945C4350B68B8E4C2233f",
                                    "logoURI": "https://app.aave.com/icons/tokens/fxs.svg",
                                    "symbol": "FXS"
                                },
                                "crvUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf939E0A03FB07F59A73314E73794Be0E57ac1b4E",
                                    "A_TOKEN": "0xb82fa9f31612989525992FCfBB09AB22Eff5c85A",
                                    "S_TOKEN": "0xb55C604075D79486b8A329c396Fc711Be54B5330",
                                    "V_TOKEN": "0x028f7886F3e937f8479efaD64f31B3fE1119857a",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x02AeE5b225366302339748951E1a924617b8814F",
                                    "STATA_TOKEN": "0x848107491E029AFDe0AC543779c7790382f15929",
                                    "logoURI": "https://app.aave.com/icons/tokens/crvusd.svg",
                                    "symbol": "crvUSD"
                                },
                                "PYUSD": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x6c3ea9036406852006290770BEdFcAbA0e23A0e8",
                                    "A_TOKEN": "0x0C0d01AbF3e6aDfcA0989eBbA9d6e85dD58EaB1E",
                                    "S_TOKEN": "0x5B393DB4c72B1Bd82CE2834F6485d61b137Bc7aC",
                                    "V_TOKEN": "0x57B67e4DE077085Fd0AF2174e9c14871BE664546",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x150bAe7Ce224555D39AfdBc6Cb4B8204E594E022",
                                    "STATA_TOKEN": "0x00F2a835758B33f3aC53516Ebd69f3dc77B0D152",
                                    "logoURI": "https://app.aave.com/icons/tokens/pyusd.svg",
                                    "symbol": "PYUSD"
                                },
                                "weETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xCd5fE23C85820F7B72D0926FC9b05b43E359b7ee",
                                    "A_TOKEN": "0xBdfa7b7893081B35Fb54027489e2Bc7A38275129",
                                    "S_TOKEN": "0xBad6eF8e76E26F39e985474aD0974FDcabF85d37",
                                    "V_TOKEN": "0x77ad9BF13a52517AD698D65913e8D381300c8Bf3",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xf112aF6F0A332B815fbEf3Ff932c057E570b62d3",
                                    "logoURI": "https://app.aave.com/icons/tokens/weeth.svg",
                                    "symbol": "weETH"
                                },
                                "osETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf1C9acDc66974dFB6dEcB12aA385b9cD01190E38",
                                    "A_TOKEN": "0x927709711794F3De5DdBF1D176bEE2D55Ba13c21",
                                    "S_TOKEN": "0x48Fa27f511F40d16f9E7C913e9388d52d95bC6d2",
                                    "V_TOKEN": "0x8838eefF2af391863E1Bb8b1dF563F86743a8470",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x0A2AF898cEc35197e6944D9E0F525C2626393442",
                                    "logoURI": "https://app.aave.com/icons/tokens/oseth.svg",
                                    "symbol": "osETH"
                                },
                                "USDe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4c9EDD5852cd905f086C759E8383e09bff1E68B3",
                                    "A_TOKEN": "0x4F5923Fc5FD4a93352581b38B7cD26943012DECF",
                                    "S_TOKEN": "0x43Cc8AD0c223b38D9c04802bB184A2D97e497D38",
                                    "V_TOKEN": "0x015396E1F286289aE23a762088E863b3ec465145",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0x55B6C4D3E8A27b8A1F5a263321b602e0fdEEcC17",
                                    "logoURI": "https://app.aave.com/icons/tokens/usde.svg",
                                    "symbol": "USDe"
                                },
                                "ETHx": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xA35b1B31Ce002FBF2058D22F30f95D405200A15b",
                                    "A_TOKEN": "0x1c0E06a0b1A4c160c17545FF2A951bfcA57C0002",
                                    "S_TOKEN": "0xBDfa7DE5CF7a7DdE4F023Cac842BF520fcF5395C",
                                    "V_TOKEN": "0x08a8Dc81AeA67F84745623aC6c72CDA3967aab8b",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xD6270dAabFe4862306190298C2B48fed9e15C847",
                                    "logoURI": "https://app.aave.com/icons/tokens/ethx.svg",
                                    "symbol": "ETHx"
                                },
                                "sUSDe": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9D39A5DE30e57443BfF2A8307A4256c8797A3497",
                                    "A_TOKEN": "0x4579a27aF00A62C0EB156349f31B345c08386419",
                                    "S_TOKEN": "0xc9335dE638f4C96a8330b2FFc44353Bab58774e3",
                                    "V_TOKEN": "0xeFFDE9BFA8EC77c14C364055a200746d6e12BeD6",
                                    "INTEREST_RATE_STRATEGY": "0x847A3364Cc5fE389283bD821cfC8A477288D9e82",
                                    "ORACLE": "0xb37aE8aBa6C0C1Bf2c509fc06E11aa4AF29B665A",
                                    "logoURI": "https://app.aave.com/icons/tokens/susde.svg",
                                    "symbol": "sUSDe"
                                }
                            }
                        },
                        "10": {
                            "address": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xDA10009cBd5D07dd0CeCc66161FC93D7c9000da1",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x1a96fe91278bcF6F19665F642FE7a88cD5c360bb",
                                    "STATA_TOKEN": "0x6dDc64289bE8a71A707fB057d5d07Cc756055d6e",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x350a791Bfc2C21F9Ed5d10980Dad2e2638ffa7f6",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xCc232dcFAAE6354cE191Bd574108c1aD03f86450",
                                    "STATA_TOKEN": "0x39BCf217ACc4Bf2fCaF7BC8800E69D986912c75e",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x7F5c764cBc14f9669B88837ca1490cCa17c31607",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x2daA7078f78485A708003989cBc9a643e3b4B61f",
                                    "STATA_TOKEN": "0x9F281eb58fd98ad98EDe0fc4C553AD4D73e7Ca2C",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC.e"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x68f180fcCe6836688e9084f035309E29Bf0A2095",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xD702DD976Fb76Fffc2D3963D037dfDae5b04E593",
                                    "STATA_TOKEN": "0x6d998FeEFC7B3664eaD09CAf02b5a0fc2E365F18",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4200000000000000000000000000000000000006",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x13e3Ee699D1909E989722E753853AE30b17e08c5",
                                    "STATA_TOKEN": "0x98d69620C31869fD4822ceb6ADAB31180475FD37",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x94b008aA00579c1307B0EF2c499aD98a8ce58e58",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x70E6DBBFFc9c3c6fB4a9c349E3101B7dCEE67f4D",
                                    "STATA_TOKEN": "0x035c93db04E5aAea54E6cd0261C492a3e0638b37",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x76FB31fb4af56892A25e32cFC43De717950c9278",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x338ed6787f463394D24813b297401B9F05a8C9d1",
                                    "STATA_TOKEN": "0xae0Ca1B1Bc6cac26981B5e2b9c40f8Ce8A9082eE",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "sUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x8c6f28f2F1A3C87F0f938b96d27520d9751ec8d9",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xC77E9CF9603F5ef5503213229ABB1Fec3001f312",
                                    "STATA_TOKEN": "0x3A956E2Fcc7e71Ea14b0257d40BEbdB287d19652",
                                    "logoURI": "https://app.aave.com/icons/tokens/susd.svg",
                                    "symbol": "sUSD"
                                },
                                "OP": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4200000000000000000000000000000000000042",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x0D276FC14719f9292D5C1eA2198673d1f4269246",
                                    "STATA_TOKEN": "0xd4F1Cf9A038269FE8F03745C2875591Ad6438ab1",
                                    "logoURI": "https://app.aave.com/icons/tokens/op.svg",
                                    "symbol": "OP"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x1F32b1c2345538c0c6f582fCB022739c4A194Ebb",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x724E47194d97263ccb71FDad84b4fed18a8be387",
                                    "STATA_TOKEN": "0xb972abef80046A57409e37a7DF5dEf2638917516",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "LUSD": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xc40F949F8a4e094D1b49a23ea9241D289B7b2819",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x8f4dAFb6Feb190e7846eb7665fD49FFb1177Ff8e",
                                    "STATA_TOKEN": "0x84648dc3Cefb601bc28a49A07a1A8Bad04D30Ad3",
                                    "logoURI": "https://app.aave.com/icons/tokens/lusd.svg",
                                    "symbol": "LUSD"
                                },
                                "MAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xdFA46478F9e5EA86d57387849598dbFB2e964b02",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xc6ac65E8f4F50a6655Efd78A92b6c503B5B625C8",
                                    "STATA_TOKEN": "0x60495bC8D8Baf7E866888ecC00491e37B47dfF24",
                                    "logoURI": "https://app.aave.com/icons/tokens/mai.svg",
                                    "symbol": "MAI"
                                },
                                "rETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9Bcef72be871e61ED4fBbc7630889beE758eb81D",
                                    "A_TOKEN": "0x724dc807b04555b71ed48a6896b6F41593b8C637",
                                    "S_TOKEN": "0xDC1fad70953Bb3918592b6fCc374fe05F5811B6a",
                                    "V_TOKEN": "0xf611aEb5013fD2c0511c9CD55c7dc5C1140741A6",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0xF17e75D58D4Be71B8e674fA104B71a827e38F087",
                                    "STATA_TOKEN": "0xf9ce3c97b4b54F3D16861420f4816D9f68190B7B",
                                    "logoURI": "https://app.aave.com/icons/tokens/reth.svg",
                                    "symbol": "rETH"
                                },
                                "USDCn": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x0b2C639c533813f4Aa9D7837CAf62653d097Ff85",
                                    "A_TOKEN": "0x38d693cE1dF5AaDF7bC62595A37D667aD57922e5",
                                    "S_TOKEN": "0x8a9FdE6925a839F6B1932d16B36aC026F8d3FbdB",
                                    "V_TOKEN": "0x5D557B07776D12967914379C71a1310e917C7555",
                                    "INTEREST_RATE_STRATEGY": "0xC2c6DF6a8B6cc79a6F927a1FFAE602c701C374Ea",
                                    "ORACLE": "0x2daA7078f78485A708003989cBc9a643e3b4B61f",
                                    "STATA_TOKEN": "0x4DD03dfD36548C840B563745e3FBeC320F37BA7e",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                }
                            }
                        },
                        "137": {
                            "address": "0x794a61358D6845594F94dc1DB02A252b5b4814aD",
                            "ASSETS": {
                                "DAI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x8f3Cf7ad23Cd3CaDbD9735AFf958023239c6A063",
                                    "A_TOKEN": "0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE",
                                    "S_TOKEN": "0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B",
                                    "V_TOKEN": "0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xF86577E7d27Ed35b85A7645c58bAaA64453fe32B",
                                    "STATA_TOKEN": "0x83c59636e602787A6EEbBdA2915217B416193FcB",
                                    "logoURI": "https://app.aave.com/icons/tokens/dai.svg",
                                    "symbol": "DAI"
                                },
                                "LINK": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x53E0bca35eC356BD5ddDFebbD1Fc0fD03FaBad39",
                                    "A_TOKEN": "0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530",
                                    "S_TOKEN": "0x89D976629b7055ff1ca02b927BA3e020F22A44e4",
                                    "V_TOKEN": "0x953A573793604aF8d41F306FEb8274190dB4aE0e",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xd9FFdb71EbE7496cC440152d43986Aae0AB76665",
                                    "STATA_TOKEN": "0x37868a45c6741616F9E5a189dC0481AD70056B6a",
                                    "logoURI": "https://app.aave.com/icons/tokens/link.svg",
                                    "symbol": "LINK"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x2791Bca1f2de4661ED88A30C99A7a9449Aa84174",
                                    "A_TOKEN": "0x625E7708f30cA75bfd92586e17077590C60eb4cD",
                                    "S_TOKEN": "0x307ffe186F84a3bc2613D1eA417A5737D69A7007",
                                    "V_TOKEN": "0xFCCf3cAbbe80101232d343252614b6A3eE81C989",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x17E33D122FC34c7ad8FBd4a1995Dff9c8aE675eb",
                                    "STATA_TOKEN": "0x1017F4a86Fc3A3c824346d0b8C5e96A5029bDAf9",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC.e"
                                },
                                "WBTC": {
                                    "decimals": 8,
                                    "UNDERLYING": "0x1BFD67037B42Cf73acF2047067bd4F2C47D9BfD6",
                                    "A_TOKEN": "0x078f358208685046a11C85e8ad32895DED33A249",
                                    "S_TOKEN": "0x633b207Dd676331c413D4C013a6294B0FE47cD0e",
                                    "V_TOKEN": "0x92b42c66840C7AD907b4BF74879FF3eF7c529473",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xc907E116054Ad103354f2D350FD2514433D57F6f",
                                    "STATA_TOKEN": "0xbC0f50CCB8514Aa7dFEB297521c4BdEBc9C7d22d",
                                    "logoURI": "https://app.aave.com/icons/tokens/wbtc.svg",
                                    "symbol": "WBTC"
                                },
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x7ceB23fD6bC0adD59E62ac25578270cFf1b9f619",
                                    "A_TOKEN": "0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8",
                                    "S_TOKEN": "0xD8Ad37849950903571df17049516a5CD4cbE55F6",
                                    "V_TOKEN": "0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xF9680D99D6C9589e2a93a78A04A279e509205945",
                                    "STATA_TOKEN": "0xb3D5Af0A52a35692D3FcbE37669b3B8C31dddE7D",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDT": {
                                    "decimals": 6,
                                    "UNDERLYING": "0xc2132D05D31c914a87C6611C10748AEb04B58e8F",
                                    "A_TOKEN": "0x6ab707Aca953eDAeFBc4fD23bA73294241490620",
                                    "S_TOKEN": "0x70eFfc565DB6EEf7B927610155602d31b670e802",
                                    "V_TOKEN": "0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xaA574f4f6E124E77a7a1B5Ed91c8b407000A7730",
                                    "STATA_TOKEN": "0x87A1fdc4C726c459f597282be639a045062c0E46",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdt.svg",
                                    "symbol": "USDT"
                                },
                                "AAVE": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xD6DF932A45C0f255f85145f286eA0b292B21C90B",
                                    "A_TOKEN": "0xf329e36C7bF6E5E86ce2150875a84Ce77f477375",
                                    "S_TOKEN": "0xfAeF6A702D15428E588d4C0614AEFb4348D83D48",
                                    "V_TOKEN": "0xE80761Ea617F66F96274eA5e8c37f03960ecC679",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x72484B12719E23115761D5DA1646945632979bB6",
                                    "STATA_TOKEN": "0xCA2E1E33E5BCF4978E2d683656E1f5610f8C4A7E",
                                    "logoURI": "https://app.aave.com/icons/tokens/aave.svg",
                                    "symbol": "AAVE"
                                },
                                "WMATIC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x0d500B1d8E8eF31E21C99d1Db9A6444d3ADf1270",
                                    "A_TOKEN": "0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97",
                                    "S_TOKEN": "0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E",
                                    "V_TOKEN": "0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xAB594600376Ec9fD91F8e885dADF0CE036862dE0",
                                    "STATA_TOKEN": "0x98254592408E389D1dd2dBa318656C2C5c305b4E",
                                    "logoURI": "https://app.aave.com/icons/tokens/wmatic.svg",
                                    "symbol": "WMATIC"
                                },
                                "CRV": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x172370d5Cd63279eFa6d502DAB29171933a610AF",
                                    "A_TOKEN": "0x513c7E3a9c69cA3e22550eF58AC1C0088e918FFf",
                                    "S_TOKEN": "0x08Cb71192985E936C7Cd166A8b268035e400c3c3",
                                    "V_TOKEN": "0x77CA01483f379E58174739308945f044e1a764dc",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x336584C8E6Dc19637A5b36206B1c79923111b405",
                                    "STATA_TOKEN": "0x4356941463eD4d75381AC23C9EF799B5d7C52AD8",
                                    "logoURI": "https://app.aave.com/icons/tokens/crv.svg",
                                    "symbol": "CRV"
                                },
                                "SUSHI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x0b3F868E0BE5597D5DB7fEB59E1CADBb0fdDa50a",
                                    "A_TOKEN": "0xc45A479877e1e9Dfe9FcD4056c699575a1045dAA",
                                    "S_TOKEN": "0x78246294a4c6fBf614Ed73CcC9F8b875ca8eE841",
                                    "V_TOKEN": "0x34e2eD44EF7466D5f9E0b782B5c08b57475e7907",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x49B0c695039243BBfEb8EcD054EB70061fd54aa0",
                                    "STATA_TOKEN": "0xe3eDe71d32240b7EC355F0e5DD1131BBe029F934",
                                    "logoURI": "https://app.aave.com/icons/tokens/sushi.svg",
                                    "symbol": "SUSHI"
                                },
                                "GHST": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x385Eeac5cB85A38A9a07A70c73e0a3271CfB54A7",
                                    "A_TOKEN": "0x8Eb270e296023E9D92081fdF967dDd7878724424",
                                    "S_TOKEN": "0x3EF10DFf4928279c004308EbADc4Db8B7620d6fc",
                                    "V_TOKEN": "0xCE186F6Cccb0c955445bb9d10C59caE488Fea559",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xDD229Ce42f11D8Ee7fFf29bDB71C7b81352e11be",
                                    "STATA_TOKEN": "0x123319636A6a9c85D9959399304F4cB23F64327e",
                                    "logoURI": "https://app.aave.com/icons/tokens/ghst.svg",
                                    "symbol": "GHST"
                                },
                                "BAL": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x9a71012B13CA4d3D0Cdc72A177DF3ef03b0E76A3",
                                    "A_TOKEN": "0x8ffDf2DE812095b1D19CB146E4c004587C0A0692",
                                    "S_TOKEN": "0xa5e408678469d23efDB7694b1B0A85BB0669e8bd",
                                    "V_TOKEN": "0xA8669021776Bc142DfcA87c21b4A52595bCbB40a",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xD106B538F2A868c28Ca1Ec7E298C3325E0251d66",
                                    "STATA_TOKEN": "0x1a8969FD39AbaF228e690B172C4C3Eb7c67F95E1",
                                    "logoURI": "https://app.aave.com/icons/tokens/bal.svg",
                                    "symbol": "BAL"
                                },
                                "DPI": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x85955046DF4668e1DD369D2DE9f3AEB98DD2A369",
                                    "A_TOKEN": "0x724dc807b04555b71ed48a6896b6F41593b8C637",
                                    "S_TOKEN": "0xDC1fad70953Bb3918592b6fCc374fe05F5811B6a",
                                    "V_TOKEN": "0xf611aEb5013fD2c0511c9CD55c7dc5C1140741A6",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x2e48b7924FBe04d575BA229A59b64547d9da16e9",
                                    "STATA_TOKEN": "0x73B788ACA5f4F0EeB3c6Da453cDf31041a77b36D",
                                    "logoURI": "https://app.aave.com/icons/tokens/dpi.svg",
                                    "symbol": "DPI"
                                },
                                "EURS": {
                                    "decimals": 2,
                                    "UNDERLYING": "0xE111178A87A3BFf0c8d18DECBa5798827539Ae99",
                                    "A_TOKEN": "0x38d693cE1dF5AaDF7bC62595A37D667aD57922e5",
                                    "S_TOKEN": "0x8a9FdE6925a839F6B1932d16B36aC026F8d3FbdB",
                                    "V_TOKEN": "0x5D557B07776D12967914379C71a1310e917C7555",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x73366Fe0AA0Ded304479862808e02506FE556a98",
                                    "STATA_TOKEN": "0x02E26888Ed3240BB38f26A2adF96Af9B52b167ea",
                                    "logoURI": "https://app.aave.com/icons/tokens/eurs.svg",
                                    "symbol": "EURS"
                                },
                                "jEUR": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x4e3Decbb3645551B8A19f0eA1678079FCB33fB4c",
                                    "A_TOKEN": "0x6533afac2E7BCCB20dca161449A13A32D391fb00",
                                    "S_TOKEN": "0x6B4b37618D85Db2a7b469983C888040F7F05Ea3D",
                                    "V_TOKEN": "0x44705f578135cC5d703b4c9c122528C73Eb87145",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x73366Fe0AA0Ded304479862808e02506FE556a98",
                                    "STATA_TOKEN": "0xD992DaC78Ef3F34614E6a7d325b7b6A320FC0AB5",
                                    "logoURI": "https://app.aave.com/icons/tokens/jeur.svg",
                                    "symbol": "jEUR"
                                },
                                "EURA": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xE0B52e49357Fd4DAf2c15e02058DCE6BC0057db4",
                                    "A_TOKEN": "0x8437d7C167dFB82ED4Cb79CD44B7a32A1dd95c77",
                                    "S_TOKEN": "0x40B4BAEcc69B882e8804f9286b12228C27F8c9BF",
                                    "V_TOKEN": "0x3ca5FA07689F266e907439aFd1fBB59c44fe12f6",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x73366Fe0AA0Ded304479862808e02506FE556a98",
                                    "STATA_TOKEN": "0xd3eb8796Ed36f58E03B7b4b5AD417FA74931d2c4",
                                    "logoURI": "https://app.aave.com/icons/tokens/eura.svg",
                                    "symbol": "EURA"
                                },
                                "miMATIC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xa3Fa99A148fA48D14Ed51d610c367C61876997F1",
                                    "A_TOKEN": "0xeBe517846d0F36eCEd99C735cbF6131e1fEB775D",
                                    "S_TOKEN": "0x687871030477bf974725232F764aa04318A8b9c8",
                                    "V_TOKEN": "0x18248226C16BF76c032817854E7C83a2113B4f06",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x4ae2Ab1af7e3b0092dbF3A4B20ec3de8fC834873",
                                    "STATA_TOKEN": "0x8486B49433cCed038b51d18Ae3772CDB7E31CA5e",
                                    "logoURI": "https://app.aave.com/icons/tokens/mimatic.svg",
                                    "symbol": "miMATIC"
                                },
                                "stMATIC": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x3A58a54C066FdC0f2D55FC9C89F0415C92eBf3C4",
                                    "A_TOKEN": "0xEA1132120ddcDDA2F119e99Fa7A27a0d036F7Ac9",
                                    "S_TOKEN": "0x1fFD28689DA7d0148ff0fCB669e9f9f0Fc13a219",
                                    "V_TOKEN": "0x6b030Ff3FB9956B1B69f475B77aE0d3Cf2CC5aFa",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x6D02E35031C4D99ee3A6A2BA47FaD0cFE355cA8f",
                                    "STATA_TOKEN": "0x867A180B7060fDC27610dC9096E93534F638A315",
                                    "logoURI": "https://app.aave.com/icons/tokens/stmatic.svg",
                                    "symbol": "stMATIC"
                                },
                                "MaticX": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xfa68FB4628DFF1028CFEc22b4162FCcd0d45efb6",
                                    "A_TOKEN": "0x80cA0d8C38d2e2BcbaB66aA1648Bd1C7160500FE",
                                    "S_TOKEN": "0x62fC96b27a510cF4977B59FF952Dc32378Cc221d",
                                    "V_TOKEN": "0xB5b46F918C2923fC7f26DB76e8a6A6e9C4347Cf9",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xB0A72A5e454890e9715e059e8df8582a6B383DE3",
                                    "STATA_TOKEN": "0xbcDd5709641Af4BE99b1470A2B3A5203539132Ec",
                                    "logoURI": "https://app.aave.com/icons/tokens/maticx.svg",
                                    "symbol": "MaticX"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x03b54A6e9a984069379fae1a4fC4dBAE93B3bCCD",
                                    "A_TOKEN": "0xf59036CAEBeA7dC4b86638DFA2E3C97dA9FcCd40",
                                    "S_TOKEN": "0x173e54325AE58B072985DbF232436961981EA000",
                                    "V_TOKEN": "0x77fA66882a8854d883101Fb8501BD3CaD347Fc32",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0xBD96b5ABBC6048c28184b462167E487533F2e35E",
                                    "STATA_TOKEN": "0x5274453F4CD5dD7280011a1Cca3B9e1b78EC59A6",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                },
                                "USDCn": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x3c499c542cEF5E3811e1192ce70d8cC03d5c3359",
                                    "A_TOKEN": "0xA4D94019934D8333Ef880ABFFbF2FDd611C762BD",
                                    "S_TOKEN": "0xc889e9f8370D14A428a9857205d99BFdB400b757",
                                    "V_TOKEN": "0xE701126012EC0290822eEA17B794454d1AF8b030",
                                    "INTEREST_RATE_STRATEGY": "0x21128C8f5AE37904c9082D932928FE0C2be1Ff73",
                                    "ORACLE": "0x17E33D122FC34c7ad8FBd4a1995Dff9c8aE675eb",
                                    "STATA_TOKEN": "0x2dCa80061632f3F87c9cA28364d1d0c30cD79a19",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                }
                            }
                        },
                        "534352": {
                            "address": "0x11fCfe756c05AD438e312a7fd934381537D3cFfe",
                            "ASSETS": {
                                "WETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0x5300000000000000000000000000000000000004",
                                    "A_TOKEN": "0xf301805bE1Df81102C957f6d4Ce29d2B8c056B2a",
                                    "S_TOKEN": "0x117d9cF336287F46DBE509a43925cFF115Aa563c",
                                    "V_TOKEN": "0xfD7344CeB1Df9Cf238EcD667f4A6F99c6Ef44a56",
                                    "INTEREST_RATE_STRATEGY": "0xEC93d0BBA1b1e635ba0Fff4786dB323db49D99F0",
                                    "ORACLE": "0x6bF14CB0A831078629D993FDeBcB182b21A8774C",
                                    "STATA_TOKEN": "0x6b9DfaC194fa78a1882680E2cE19194D006AeEfd",
                                    "logoURI": "https://app.aave.com/icons/tokens/weth.svg",
                                    "symbol": "WETH"
                                },
                                "USDC": {
                                    "decimals": 6,
                                    "UNDERLYING": "0x06eFdBFf2a14a7c8E15944D1F4A48F9F95F663A4",
                                    "A_TOKEN": "0x1D738a3436A8C49CefFbaB7fbF04B660fb528CbD",
                                    "S_TOKEN": "0x59F359aA263f7Ac09876E869AF1F75b558904ed4",
                                    "V_TOKEN": "0x3d2E209af5BFa79297C88D6b57F89d792F6E28EE",
                                    "INTEREST_RATE_STRATEGY": "0xEC93d0BBA1b1e635ba0Fff4786dB323db49D99F0",
                                    "ORACLE": "0x427Fd98dbD1DbC2D4e792350caBe7c9665F35bee",
                                    "STATA_TOKEN": "0x9fA123bC7E6b61cC8a9D893673a4C6E5392FF4A7",
                                    "logoURI": "https://app.aave.com/icons/tokens/usdc.svg",
                                    "symbol": "USDC"
                                },
                                "wstETH": {
                                    "decimals": 18,
                                    "UNDERLYING": "0xf610A9dfB7C89644979b4A0f27063E9e7d7Cda32",
                                    "A_TOKEN": "0x5B1322eeb46240b02e20062b8F0F9908d525B09c",
                                    "S_TOKEN": "0x18e3f125ce85e8D65AD2bb4f6b5fff110772A078",
                                    "V_TOKEN": "0x8a035644322129800C3f747f54Db0F4d3c0A2877",
                                    "INTEREST_RATE_STRATEGY": "0xEC93d0BBA1b1e635ba0Fff4786dB323db49D99F0",
                                    "ORACLE": "0x4EdAbf45e78363b8Dcd763bBbd05665c6e24975C",
                                    "STATA_TOKEN": "0x6e368c4dBf083e18a29aE63FC06AF9deDb3242F0",
                                    "logoURI": "https://app.aave.com/icons/tokens/wsteth.svg",
                                    "symbol": "wstETH"
                                }
                            }
                        }
                    }
                    }//if the token is ERC20 token use this contract list and function
                    }
                },
        ```

- TRANSFER
    - TRANSFER_NATIVE

        **Description:** Execute transfers of native blockchain currencies between wallet addresses, supporting different networks' native tokens (ETH, BNB, MATIC, etc.) with customizable gas settings, transaction speed, and amount specifications for secure and efficient native token transfers

        **Keywords:** transfer eth, send bnb, transfer native token, send eth, transfer matic, send native crypto, transfer avax, send sol, transfer native coin, send gas token, transfer chain token, send native currency, transfer main token, send network token, transfer base token, native transfer, send chain coin, transfer gas token, send base currency, network transfer

        ```tsx
                {
                    "action": "TRANSFER_NATIVE",
                    "network": "1",
                    "inputs": [
                        {
                            "name": "toAddress",
                            "type": "string",
                            "default": ""
                        },
                        {
                            "name": "amount",
                            "type": "string",
                            "default": ""
                        }
                    ],
                    "outputs": [
                        {
                            "name": "success",
                            "type": "boolean"
                        }
                    ],
                    "protocol": {
                        "name": ""
                    }
                },
        ```

    - TRANSFER

        **Description:** Execute transfers of ERC20, BEP20, or other standard token contracts between wallet addresses, supporting multiple token standards across different networks with customizable transaction parameters, gas settings, and transfer amounts for secure token movements

        **keywords:** transfer token, send erc20, transfer usdt, send usdc, transfer bep20, send tokens, transfer stablecoin, send token contract, transfer erc721, token movement, send contract token, transfer crypto token, send wrapped token, transfer coin, send digital token, contract transfer, erc20 movement, transfer digital asset, send custom token, transfer standard token

        ```tsx
                {
                    "action": "TRANSFER",
                    "network": "1",
                    "inputs": [
                        {
                            "name": "tokenAddress",
                            "type": "string",
                            "default": ""
                        },
                        {
                            "name": "toAddress",
                            "type": "string",
                            "default": ""
                        },
                        {
                            "name": "amount",
                            "type": "string",
                            "default": ""
                        }
                    ],
                    "outputs": [
                        {
                            "name": "success",
                            "type": "boolean"
                        }
                    ],
                    "protocol": {
                        "name": ""
                    }
                },
        ```


- STAKE
    - STAKE_DEPOSIT

        **Description:** Stake tokens into DeFi protocols for yield generation through network validation or liquidity provision, supporting various staking mechanisms with customizable lock periods, reward rates, and staking parameters for optimized yield earning through protocol participation

        **Keywords:** stake tokens, deposit stake, staking deposit, stake crypto, deposit for staking, stake for rewards, staking tokens, deposit to earn, stake and earn, deposit validator, staking rewards, stake for yield, deposit staking pool, stake position, deposit for rewards, staking entry, stake allocation, deposit stake tokens, staking initialization, stake placement

        ```tsx
        {
                    "action": "STAKE_DEPOSIT",
                    "network": "1",
                    "inputs": [
                        {
                            "name": "poolId",
                            "type": "string",
                            "default": ""
                        },
                        {
                            "name": "amount",
                            "type": "string",
                            "default": ""
                        }
                    ],
                    "outputs": [
                        {
                            "name": "success",
                            "type": "boolean"
                        }
                    ],
                    "protocol": {
                        "solv": {
                        "contract": {
                            "1": {
                                "address": "0x1fF7d7C0A7D8E94046708C611DeC5056A9d2B823",
                                "depositToken": "0xC96dE26018A54D51c097160568752c4E3BD6C364",
                                "solvBTC": "0x7A56E1C57C7475CCf742a1832B028F0456652F97",
                                "poolId": "0x2dc130e46b5958208155546bd4049d5b3319798063a8c4180b4b2b82f3ebdc3d"

                            },
                            "56": {
                                "address": "0x5c1215712F174dF2Cbc653eDce8B53FA4CAF2201",
                                "depositToken": "0x7130d2A12B9BCbFAe4f2634d864A1Ee1Ce3Ead9c",
                                "solvBTC": "0x4aae823a6a0b376de6a78e74ecc5b079d38cbcf7",
                                "poolId": "0xafb1107b43875eb79f72e3e896933d4f96707451c3d5c32741e8e05410b321d8"

                            },
                            "42161": {
                                "address": "0xe9eD7530427Cb41A56C9e004e00e074cCc168C44",
                                "depositToken": "0x2f2a2543B76A4166549F7aaB2e75Bef0aefC5B0f",
                                "solvBTC": "0x3647c54c4c2C65bC7a2D63c0Da2809B399DBBDC0",
                                "poolId": "0x488def4a346b409d5d57985a160cd216d29d4f555e1b716df4e04e2374d2d9f6"

                            }
                        },
                        "function": "createSubscription"
                        }
                    }
                },
        ```

    - STAKE_WITHDRAW

        **Description:** Remove staked tokens and accumulated rewards from staking protocols, supporting various withdrawal mechanisms including unstaking periods, instant withdrawals with fees, reward claims, and exit from staking positions with consideration for lock periods and protocol conditions

        **Keywords:** unstake tokens, withdraw stake, remove staked, unstaking withdrawal, claim rewards, withdraw staking, unstake position, remove stake, withdraw rewards, claim staked, unstake crypto, withdraw from staking, remove staking, unstaking tokens, claim position, withdraw validator, unstake and claim, remove from staking, withdrawal from stake, unstake rewards Copy

        ```tsx
                {
                    "action": "STAKE_WITHDRAW",
                    "network": "1",
                    "inputs": [
                        {
                            "name": "poolId",
                            "type": "string",
                            "default": ""
                        },
                        {
                            "name": "amount",
                            "type": "string",
                            "default": ""
                        }
                    ],
                    "outputs": [
                        {
                            "name": "success",
                            "type": "boolean"
                        }
                    ],
                    "protocol": {
                        "solv": {
                        "contract": {
                            "1": {
                                "address": "0x1fF7d7C0A7D8E94046708C611DeC5056A9d2B823",
                                "depositToken": "0xC96dE26018A54D51c097160568752c4E3BD6C364",
                                "solvBTC": "0x7A56E1C57C7475CCf742a1832B028F0456652F97",
                                "poolId": "0x2dc130e46b5958208155546bd4049d5b3319798063a8c4180b4b2b82f3ebdc3d"

                            },
                            "56": {
                                "address": "0x5c1215712F174dF2Cbc653eDce8B53FA4CAF2201",
                                "depositToken": "0x7130d2A12B9BCbFAe4f2634d864A1Ee1Ce3Ead9c",
                                "solvBTC": "0x4aae823a6a0b376de6a78e74ecc5b079d38cbcf7",
                                "poolId": "0xafb1107b43875eb79f72e3e896933d4f96707451c3d5c32741e8e05410b321d8"

                            },
                            "42161": {
                                "address": "0xe9eD7530427Cb41A56C9e004e00e074cCc168C44",
                                "depositToken": "0x2f2a2543B76A4166549F7aaB2e75Bef0aefC5B0f",
                                "solvBTC": "0x3647c54c4c2C65bC7a2D63c0Da2809B399DBBDC0",
                                "poolId": "0x488def4a346b409d5d57985a160cd216d29d4f555e1b716df4e04e2374d2d9f6"

                            }
                        },
                        "function": "createRedemption"
                        }
                    }
                }
        ```