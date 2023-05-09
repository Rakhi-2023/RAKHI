# Whitepaper 1.0.0.1 Español Token Rakhi (RKI)

## Binance Smart Chain (BSC)

Nuestro contrato inteligente es BEP-20. Para obtener detalles técnicos sobre el estándar BEP-20: https://academy.binance.com/en/glossary/bep-20

Rakhi (RKI) token desarrollado en Solidity. Asegúrese de consultar su tutorial: https://solidity.readthedocs.io/en/v0.6.9/introduction-to-smart-contracts.html

Implementaciones de estándares ERC20

Source code: 

## OpenZeppelin - Implementación segura

Nuestros Smart Contracts se basan en seguros y confiables [OpenZeppelin ERC-20 Smart Contract](https://docs.openzeppelin.com/contracts/4.x/erc20)

OpenZeppelin el código está en el corazón de nuestros tokens y seguimos sus prácticas de seguridad e implementación con mucho cuidado.

# Token Rakhi (RKI) 

Este token es una implementación estándar de ERC-20 y se implementó en la red principal de Binance Smart Chain con un suministro máximo fijo de 1,000,000 RKI. 

Mainnet Deployed Rakhi (RKI) Token can be found here: 

Parámetros de compilación: Solidity 0.8.18+commit.fc410830. Optimización 200

## Proyecto Rakhi (RKI)
Nuestro proyecto nació el 25 de Marzo de 2023  y se almaceno en la red BSC maint con el contrato 0xd1245aD8E7d3a2727F2d592eb078930889AF4d65, nombre nativa Rakhi (RKI). Evolucionó con el whitepaper 1.0.0.1 donde se inicia el fondos de inversión y comercialización de productos gracias a nuestra empresa aliada blackzone.

* Link Whitepaper 1.0.0.1 Rakhi (RKI).
* Contrato: https://bscscan.com/token/0xd1245ad8e7d3a2727f2d592eb078930889af4d65


## Criptomoneda Rakhi (RKI) Blockchain 2023 
El Proyecto de Comercio Rakhi en su etapa de creación fue presentado a la comunidad como el activo digital  para alcanzar un apalancamiento en base de prueba de comercio, logrando posicionamiento y reconocimiento . las pruebas se iniciaron sobre la red de Ether en el contrato 25 de enero 2023, smart contract: https://etherscan.io/address/0xd1245aD8E7d3a2727F2d592eb078930889AF4d65 

* Link Código Rakhi blockchain
https://github.com/rki/rki/blob/main/rki.sol

## Característica Rakhi
* Nombre  Rakhi
* Abreviatura RKI
* Red: Binance Smart Chain (BSC)
* Network: Maint BSC
* Smart Contrac: 0xd1245aD8E7d3a2727F2d592eb078930889AF4d65
* Total coin supply: 1.000.000 coins

// contracts/BEP20.sol
* Source Code: https://github.com/rki/rki
* Link Contract: https://bscscan.com/token/0xd1245aD8E7d3a2727F2d592eb078930889AF4d65#code

* /// @custom:security-contact info@rakhi.io
* /***********************************************************
* Rakhi (RKI) cryptocurrency backup and investment toke
* ************************************************************/  
* // Copyright (c) 2023 Rakhi (RKI)
/*--------------------------------------------------------------- @dev
 * Exclusive premier investment pool for the community RKI Token
 * maximum profitability and liquidity. converts RKI Token.
*/

/* < Block Genesis Token >
 - Total Supply: 1.000.000 RKI token
 - Initial Supply: 1.000.000 RKI Token
 
 Details Pool Bep20
 Wallet: 

## Desarrollo:

# 1 Fase:
Creación e Implementación del Contrato Token RKI.

# 2 Fase:
Capacitación y Promoción en la Comunidad RKI.

# 3 Fase:
Intercambio y procesador de Pago.

# 4 Fase:
Adopción en mercado local.

# 5 Fase:
Lanzamiento Internacional.

## Roadmap

# Q1 2020
* Enero 25 de 2023: Creación del Token RKI (Test).

# Q1 2022
* Febrero 3. Creación y Lanzamiento Token RKI
* (1 phase)

# Q2 2022
* Febrero a Marzo - Venta de activos a través de corredores de bolsa y / o corredores.
* Capacitación comunidad.

# Q3 2022
* Marzo a Junio - Adopción local.

# Q4 2022
* Junio - Diciembre Fase 3.

# Q1 2023
* Enero - Lanzamiento Internacional.

## Bibliotecas e interfaces

```Solidity
pragma solidity ^0.8.2;
```
Nosotros hemos desplegado Rakhi (RKI) token to mainnet with solidity ^0.8.2.

```Solidity
import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
```
De inmediato nos adentramos en el uso intensivo de las bibliotecas seguras de OpenZeppelin. Esta es la implementación básica de ERC-20 en la que se basa RKI.

```Solidity
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Snapshot.sol";
import "@openzeppelin/contracts/access/AccessControl.sol";
import "@openzeppelin/contracts/security/Pausable.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";
```
Ya hemos incluido rki.sol, ¿por qué incluir la interfaz? El contrato inteligente de RKI acepta un _token como uno de los parámetros de construcción. Discutiremos esto en la sección ** constructor ** a continuación.

## ERC20Burnable
Nuestro Token puede realizar la función de Burning Token, realizar Recompras para poder Quemar Tokens.

** _burn(account, amount); **

Code:

```Solidity
/**
 * @dev Extension of {ERC20} that allows token holders to destroy both their own
 * tokens and those that they have an allowance for, in a way that can be
 * recognized off-chain (via event analysis).
 */
abstract contract ERC20Burnable is Context, ERC20 {
    /**
     * @dev Destroys `amount` tokens from the caller.
     *
     * See {ERC20-_burn}.
     */
    function burn(uint256 amount) public virtual {
        _burn(_msgSender(), amount);
    }
    /**
     * @dev Destroys `amount` tokens from `account`, deducting from the caller's
     * allowance.
     *
     * See {ERC20-_burn} and {ERC20-allowance}.
     *
     * Requirements:
     *
     * - the caller must have allowance for ``accounts``'s tokens of at least
     * `amount`.
     */
    function burnFrom(address account, uint256 amount) public virtual {
        uint256 currentAllowance = allowance(account, _msgSender());
        require(currentAllowance >= amount, "ERC20: burn amount exceeds allowance");
        unchecked {
            _approve(account, _msgSender(), currentAllowance - amount);
        }
        _burn(account, amount);
    }
}
// File: contracts/rki.sol
```

## ERC20Snapshot
Con la función Snapshop nos permite obtener soporte del token en cualquier momento para tenerlo para consultas por temporadas definidas por una consecutiva, o tomar saldos de todos los titulares.

** _snapshot(); **

Code:

```Solidity
abstract contract ERC20Snapshot is ERC20 {
    // Inspired by Jordi Baylina's MiniMeToken to record historical balances:
    // https://github.com/Giveth/minimd/blob/ea04d950eea153a04c51fa510b068b9dded390cb/contracts/MiniMeToken.sol
    using Arrays for uint256[];
    using Counters for Counters.Counter;
    // Snapshotted values have arrays of ids and the value corresponding to that id. These could be an array of a
    // Snapshot struct, but that would impede usage of functions that work on an array.
    struct Snapshots {
        uint256[] ids;
        uint256[] values;
    }
    mapping(address => Snapshots) private _accountBalanceSnapshots;
    Snapshots private _totalSupplySnapshots;
    // Snapshot ids increase monotonically, with the first value being 1. An id of 0 is invalid.
    Counters.Counter private _currentSnapshotId;
    /**
     * @dev Emitted by {_snapshot} when a snapshot identified by `id` is created.
     */
    event Snapshot(uint256 id);
    /**
     * @dev Creates a new snapshot and returns its snapshot id.
     *
     * Emits a {Snapshot} event that contains the same id.
     *
     * {_snapshot} is `internal` and you have to decide how to expose it externally. Its usage may be restricted to a
     * set of accounts, for example using {AccessControl}, or it may be open to the public.
     *
     * [WARNING]
     * ====
     * While an open way of calling {_snapshot} is required for certain trust minimization mechanisms such as forking,
     * you must consider that it can potentially be used by attackers in two ways.
     *
     * First, it can be used to increase the cost of retrieval of values from snapshots, although it will grow
     * logarithmically thus rendering this attack ineffective in the long term. Second, it can be used to target
     * specific accounts and increase the cost of ERC20 transfers for them, in the ways specified in the Gas Costs
     * section above.
     *
     * We haven't measured the actual numbers; if this is something you're interested in please reach out to us.
     * ====
     */
    function _snapshot() internal virtual returns (uint256) {
        _currentSnapshotId.increment();
        uint256 currentId = _getCurrentSnapshotId();
        emit Snapshot(currentId);
        return currentId;
    }
    /**
     * @dev Get the current snapshotId
     */
    function _getCurrentSnapshotId() internal view virtual returns (uint256) {
        return _currentSnapshotId.current();
    }
    /**
     * @dev Retrieves the balance of `account` at the time `snapshotId` was created.
     */
    function balanceOfAt(address account, uint256 snapshotId) public view virtual returns (uint256) {
        (bool snapshotted, uint256 value) = _valueAt(snapshotId, _accountBalanceSnapshots[account]);
        return snapshotted ? value : balanceOf(account);
    }
    /**
     * @dev Retrieves the total supply at the time `snapshotId` was created.
     */
    function totalSupplyAt(uint256 snapshotId) public view virtual returns (uint256) {
        (bool snapshotted, uint256 value) = _valueAt(snapshotId, _totalSupplySnapshots);
        return snapshotted ? value : totalSupply();
    }
    // Update balance and/or total supply snapshots before the values are modified. This is implemented
    // in the _beforeTokenTransfer hook, which is executed for _mint, _burn, and _transfer operations.
    function _beforeTokenTransfer(
        address from,
        address to,
        uint256 amount
    ) internal virtual override {
        super._beforeTokenTransfer(from, to, amount);
        if (from == address(0)) {
            // mint
            _updateAccountSnapshot(to);
            _updateTotalSupplySnapshot();
        } else if (to == address(0)) {
            // burn
            _updateAccountSnapshot(from);
            _updateTotalSupplySnapshot();
        } else {
            // transfer
            _updateAccountSnapshot(from);
            _updateAccountSnapshot(to);
        }
    }
    function _valueAt(uint256 snapshotId, Snapshots storage snapshots) private view returns (bool, uint256) {
        require(snapshotId > 0, "ERC20Snapshot: id is 0");
        require(snapshotId <= _getCurrentSnapshotId(), "ERC20Snapshot: nonexistent id");
        // When a valid snapshot is queried, there are three possibilities:
        //  a) The queried value was not modified after the snapshot was taken. Therefore, a snapshot entry was never
        //  created for this id, and all stored snapshot ids are smaller than the requested one. The value that corresponds
        //  to this id is the current one.
        //  b) The queried value was modified after the snapshot was taken. Therefore, there will be an entry with the
        //  requested id, and its value is the one to return.
        //  c) More snapshots were created after the requested one, and the queried value was later modified. There will be
        //  no entry for the requested id: the value that corresponds to it is that of the smallest snapshot id that is
        //  larger than the requested one.
        //
        // In summary, we need to find an element in an array, returning the index of the smallest value that is larger if
        // it is not found, unless said value doesn't exist (e.g. when all values are smaller). Arrays.findUpperBound does
        // exactly this.
        uint256 index = snapshots.ids.findUpperBound(snapshotId);
        if (index == snapshots.ids.length) {
            return (false, 0);
        } else {
            return (true, snapshots.values[index]);
        }
    }
    function _updateAccountSnapshot(address account) private {
        _updateSnapshot(_accountBalanceSnapshots[account], balanceOf(account));
    }
    function _updateTotalSupplySnapshot() private {
        _updateSnapshot(_totalSupplySnapshots, totalSupply());
    }
    function _updateSnapshot(Snapshots storage snapshots, uint256 currentValue) private {
        uint256 currentId = _getCurrentSnapshotId();
        if (_lastSnapshotId(snapshots.ids) < currentId) {
            snapshots.ids.push(currentId);
            snapshots.values.push(currentValue);
        }
    }
    function _lastSnapshotId(uint256[] storage ids) private view returns (uint256) {
        if (ids.length == 0) {
            return 0;
        } else {
            return ids[ids.length - 1];
        }
    }
}
// File: contracts/granacoin.sol
```

## AccessControl
El control de acceso, es decir, "a quién se le permite hacer esto", es increíblemente importante en el mundo de los contratos inteligentes. El control de acceso de su contrato puede regir quién puede acuñar tokens, congelar transferencias y muchas otras cosas. Por lo tanto, es fundamental comprender cómo lo implementa, no sea que alguien más robe todo su sistema.

Code:

```Solidity
pragma solidity ^0.8.0;
/**
 * @dev String operations.
 */
library Strings {
    bytes16 private constant _HEX_SYMBOLS = "0123456789abcdef";
    /**
     * @dev Converts a `uint256` to its ASCII `string` decimal representation.
     */
    function toString(uint256 value) internal pure returns (string memory) {
        // Inspired by OraclizeAPI's implementation - MIT licence
        // https://github.com/oraclize/ethereum-api/blob/b42146b063c7d6ee1358846c198246239e9360e8/oraclizeAPI_0.4.25.sol
        if (value == 0) {
            return "0";
        }
        uint256 temp = value;
        uint256 digits;
        while (temp != 0) {
            digits++;
            temp /= 10;
        }
        bytes memory buffer = new bytes(digits);
        while (value != 0) {
            digits -= 1;
            buffer[digits] = bytes1(uint8(48 + uint256(value % 10)));
            value /= 10;
        }
        return string(buffer);
    }
    /**
     * @dev Converts a `uint256` to its ASCII `string` hexadecimal representation.
     */
    function toHexString(uint256 value) internal pure returns (string memory) {
        if (value == 0) {
            return "0x00";
        }
        uint256 temp = value;
        uint256 length = 0;
        while (temp != 0) {
            length++;
            temp >>= 8;
        }
        return toHexString(value, length);
    }
    /**
     * @dev Converts a `uint256` to its ASCII `string` hexadecimal representation with fixed length.
     */
    function toHexString(uint256 value, uint256 length) internal pure returns (string memory) {
        bytes memory buffer = new bytes(2 * length + 2);
        buffer[0] = "0";
        buffer[1] = "x";
        for (uint256 i = 2 * length + 1; i > 1; --i) {
            buffer[i] = _HEX_SYMBOLS[value & 0xf];
            value >>= 4;
        }
        require(value == 0, "Strings: hex length insufficient");
        return string(buffer);
    }
}
// File: @openzeppelin/contracts/access/IAccessControl.sol
```

## Pausable
la capacidad de realizar todas las operaciones del sistema con el administrador del sistema, esto permite evitar pérdidas.

Code:

```Solidity
pragma solidity ^0.8.0;
/**
 * @dev Provides information about the current execution context, including the
 * sender of the transaction and its data. While these are generally available
 * via msg.sender and msg.data, they should not be accessed in such a direct
 * manner, since when dealing with meta-transactions the account sending and
 * paying for execution may not be the actual sender (as far as an application
 * is concerned).
 *
 * This contract is only required for intermediate, library-like contracts.
 */
abstract contract Context {
    function _msgSender() internal view virtual returns (address) {
        return msg.sender;
    }
    function _msgData() internal view virtual returns (bytes calldata) {
        return msg.data;
    }
}
// File: @openzeppelin/contracts/security/Pausable.sol
```
## Compilación:
* Compiler debug log:
* Note: Contract was created during TxHash# 0x0d27f78b90bc644ebdd46c0419091e6536fdfb49e1216e9eb8c29fedaf46dec1
* Successfully generated ByteCode and ABI for Contract Address [0xd1245aD8E7d3a2727F2d592eb078930889AF4d65]

 < Compiler Version: v0.8.18+commit.87f61d96 > 
 Optimization Enabled: 1
* Runs: 200
* ContractName: RKI
* ContractBytecode:
```
6101406040523480156200001257600080fd5b506040518060400160405280600581526020016452414b484960d81b81525080604051806040016040528060018152602001603160f81b8152506040518060400160405280600581526020016452414b484960d81b81525060405180604001604052806003815260200162524b4960e81b815250816003908162000097919062000547565b506004620000a6828262000547565b505050620000c3620000bd6200018e60201b60201c565b62000192565b6009805460ff60a01b19169055815160209283012081519183019190912060e08290526101008190524660a0818152604080517f8b73c3c69bb8fe3d512ecc4cf759cc79239f7b179b0ffacaa9a75d522b39400f818801819052818301969096526060810194909452608080850193909352308483018190528151808603909301835260c09485019091528151919095012090529190915261012052506200018833620001736012600a62000728565b6200018290620f424062000740565b620001e4565b6200079c565b3390565b600980546001600160a01b038381166001600160a01b0319831681179093556040519116919082907f8be0079c531659141344cd1fd0a4f28419497f9722a3daafe3b4186f6b6457e090600090a35050565b6001600160a01b038216620002405760405162461bcd60e51b815260206004820152601f60248201527f45524332303a206d696e7420746f20746865207a65726f20616464726573730060448201526064015b60405180910390fd5b6200024e60008383620002b9565b80600260008282546200026291906200075a565b90915550506001600160a01b038216600081815260208181526040808320805486019055518481527fddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef910160405180910390a35050565b620002c3620002e0565b620002db8383836200033860201b620008351760201c565b505050565b620002f4600954600160a01b900460ff1690565b15620003365760405162461bcd60e51b815260206004820152601060248201526f14185d5cd8589b194e881c185d5cd95960821b604482015260640162000237565b565b62000350838383620002db60201b620008541760201c565b6001600160a01b03831662000374576200036a826200039f565b620002db620003d7565b6001600160a01b0382166200038e576200036a836200039f565b62000399836200039f565b620002db825b6001600160a01b03811660009081526005602090815260408083209183905290912054620003d49190620003e7565b620003e7565b50565b620003366006620003ce60025490565b6000620003f362000436565b905080620004018462000454565b1015620002db578254600180820185556000858152602080822090930193909355938401805494850181558252902090910155565b60006200044f60086200049f60201b620008821760201c565b905090565b805460009081036200046857506000919050565b815482906200047a9060019062000770565b815481106200048d576200048d62000786565b90600052602060002001549050919050565b5490565b634e487b7160e01b600052604160045260246000fd5b600181811c90821680620004ce57607f821691505b602082108103620004ef57634e487b7160e01b600052602260045260246000fd5b50919050565b601f821115620002db57600081815260208120601f850160051c810160208610156200051e5750805b601f850160051c820191505b818110156200053f578281556001016200052a565b505050505050565b81516001600160401b03811115620005635762000563620004a3565b6200057b81620005748454620004b9565b84620004f5565b602080601f831160018114620005b357600084156200059a5750858301515b600019600386901b1c1916600185901b1785556200053f565b600085815260208120601f198616915b82811015620005e457888601518255948401946001909101908401620005c3565b5085821015620006035787850151600019600388901b60f8161c191681555b5050505050600190811b01905550565b634e487b7160e01b600052601160045260246000fd5b600181815b808511156200066a5781600019048211156200064e576200064e62000613565b808516156200065c57918102915b93841c93908002906200062e565b509250929050565b600082620006835750600162000722565b81620006925750600062000722565b8160018114620006ab5760028114620006b657620006d6565b600191505062000722565b60ff841115620006ca57620006ca62000613565b50506001821b62000722565b5060208310610133831016604e8410600b8410161715620006fb575081810a62000722565b62000707838362000629565b80600019048211156200071e576200071e62000613565b0290505b92915050565b60006200073960ff84168362000672565b9392505050565b808202811582820484141762000722576200072262000613565b8082018082111562000722576200072262000613565b8181038181111562000722576200072262000613565b634e487b7160e01b600052603260045260246000fd5b60805160a05160c05160e051610100516101205161193a620007ec6000396000610c5d01526000610cac01526000610c8701526000610be001526000610c0a01526000610c34015261193a6000f3fe608060405234801561001057600080fd5b506004361061018e5760003560e01c8063715018a6116100de5780639711715a11610097578063a9059cbb11610071578063a9059cbb14610328578063d505accf1461033b578063dd62ed3e1461034e578063f2fde38b1461036157600080fd5b80639711715a146102fa578063981b24d014610302578063a457c2d71461031557600080fd5b8063715018a6146102a157806379cc6790146102a95780637ecebe00146102bc5780638456cb59146102cf5780638da5cb5b146102d757806395d89b41146102f257600080fd5b8063395093511161014b57806342966c681161012557806342966c68146102405780634ee2cd7e146102535780635c975abb1461026657806370a082311461027857600080fd5b806339509351146102105780633f4ba83a1461022357806340c10f191461022d57600080fd5b806306fdde0314610193578063095ea7b3146101b157806318160ddd146101d457806323b872dd146101e6578063313ce567146101f95780633644e51514610208575b600080fd5b61019b610374565b6040516101a891906116a1565b60405180910390f35b6101c46101bf366004611706565b610406565b60405190151581526020016101a8565b6002545b6040519081526020016101a8565b6101c46101f4366004611730565b610420565b604051601281526020016101a8565b6101d8610444565b6101c461021e366004611706565b610453565b61022b610475565b005b61022b61023b366004611706565b610487565b61022b61024e36600461176c565b61049d565b6101d8610261366004611706565b6104aa565b600954600160a01b900460ff166101c4565b6101d8610286366004611785565b6001600160a01b031660009081526020819052604090205490565b61022b610503565b61022b6102b7366004611706565b610515565b6101d86102ca366004611785565b61052a565b61022b610548565b6009546040516001600160a01b0390911681526020016101a8565b61019b610558565b61022b610567565b6101d861031036600461176c565b610577565b6101c4610323366004611706565b6105a2565b6101c4610336366004611706565b610622565b61022b6103493660046117a0565b610630565b6101d861035c366004611813565b610794565b61022b61036f366004611785565b6107bf565b60606003805461038390611846565b80601f01602080910402602001604051908101604052809291908181526020018280546103af90611846565b80156103fc5780601f106103d1576101008083540402835291602001916103fc565b820191906000526020600020905b8154815290600101906020018083116103df57829003601f168201915b5050505050905090565b600033610414818585610886565b60019150505b92915050565b60003361042e8582856109aa565b610439858585610a24565b506001949350505050565b600061044e610bd3565b905090565b6000336104148185856104668383610794565b6104709190611890565b610886565b61047d610cfa565b610485610d54565b565b61048f610cfa565b6104998282610da9565b5050565b6104a73382610e74565b50565b6001600160a01b0382166000908152600560205260408120819081906104d1908590610fb2565b91509150816104f8576001600160a01b0385166000908152602081905260409020546104fa565b805b95945050505050565b61050b610cfa565b61048560006110a8565b6105208233836109aa565b6104998282610e74565b6001600160a01b0381166000908152600a602052604081205461041a565b610550610cfa565b6104856110fa565b60606004805461038390611846565b61056f610cfa565b6104a761113d565b6000806000610587846006610fb2565b91509150816105985760025461059a565b805b949350505050565b600033816105b08286610794565b9050838110156106155760405162461bcd60e51b815260206004820152602560248201527f45524332303a2064656372656173656420616c6c6f77616e63652062656c6f77604482015264207a65726f60d81b60648201526084015b60405180910390fd5b6104398286868403610886565b600033610414818585610a24565b834211156106805760405162461bcd60e51b815260206004820152601d60248201527f45524332305065726d69743a206578706972656420646561646c696e65000000604482015260640161060c565b60007f6e71edae12b1b97f4d1f60370fef10105fa2faae0126114a169c64845d6126c98888886106af8c611197565b6040805160208101969096526001600160a01b0394851690860152929091166060840152608083015260a082015260c0810186905260e001604051602081830303815290604052805190602001209050600061070a826111bf565b9050600061071a8287878761120d565b9050896001600160a01b0316816001600160a01b03161461077d5760405162461bcd60e51b815260206004820152601e60248201527f45524332305065726d69743a20696e76616c6964207369676e61747572650000604482015260640161060c565b6107888a8a8a610886565b50505050505050505050565b6001600160a01b03918216600090815260016020908152604080832093909416825291909152205490565b6107c7610cfa565b6001600160a01b03811661082c5760405162461bcd60e51b815260206004820152602660248201527f4f776e61626c653a206e6577206f776e657220697320746865207a65726f206160448201526564647265737360d01b606482015260840161060c565b6104a7816110a8565b6001600160a01b0383166108595761084c82611235565b610854611267565b505050565b6001600160a01b0382166108705761084c83611235565b61087983611235565b61085482611235565b5490565b6001600160a01b0383166108e85760405162461bcd60e51b8152602060048201526024808201527f45524332303a20617070726f76652066726f6d20746865207a65726f206164646044820152637265737360e01b606482015260840161060c565b6001600160a01b0382166109495760405162461bcd60e51b815260206004820152602260248201527f45524332303a20617070726f766520746f20746865207a65726f206164647265604482015261737360f01b606482015260840161060c565b6001600160a01b0383811660008181526001602090815260408083209487168084529482529182902085905590518481527f8c5be1e5ebec7d5bd14f71427d1e84f3dd0314c0f7b2291e5b200ac8c7c3b925910160405180910390a3505050565b60006109b68484610794565b90506000198114610a1e5781811015610a115760405162461bcd60e51b815260206004820152601d60248201527f45524332303a20696e73756666696369656e7420616c6c6f77616e6365000000604482015260640161060c565b610a1e8484848403610886565b50505050565b6001600160a01b038316610a885760405162461bcd60e51b815260206004820152602560248201527f45524332303a207472616e736665722066726f6d20746865207a65726f206164604482015264647265737360d81b606482015260840161060c565b6001600160a01b038216610aea5760405162461bcd60e51b815260206004820152602360248201527f45524332303a207472616e7366657220746f20746865207a65726f206164647260448201526265737360e81b606482015260840161060c565b610af5838383611275565b6001600160a01b03831660009081526020819052604090205481811015610b6d5760405162461bcd60e51b815260206004820152602660248201527f45524332303a207472616e7366657220616d6f756e7420657863656564732062604482015265616c616e636560d01b606482015260840161060c565b6001600160a01b03848116600081815260208181526040808320878703905593871680835291849020805487019055925185815290927fddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef910160405180910390a3610a1e565b6000306001600160a01b037f000000000000000000000000000000000000000000000000000000000000000016148015610c2c57507f000000000000000000000000000000000000000000000000000000000000000046145b15610c5657507f000000000000000000000000000000000000000000000000000000000000000090565b50604080517f00000000000000000000000000000000000000000000000000000000000000006020808301919091527f0000000000000000000000000000000000000000000000000000000000000000828401527f000000000000000000000000000000000000000000000000000000000000000060608301524660808301523060a0808401919091528351808403909101815260c0909201909252805191012090565b6009546001600160a01b031633146104855760405162461bcd60e51b815260206004820181905260248201527f4f776e61626c653a2063616c6c6572206973206e6f7420746865206f776e6572604482015260640161060c565b610d5c611288565b6009805460ff60a01b191690557f5db9ee0a495bf2e6ff9c91a7834c1ba4fdd244a5e8aa4e537bd38aeae4b073aa335b6040516001600160a01b03909116815260200160405180910390a1565b6001600160a01b038216610dff5760405162461bcd60e51b815260206004820152601f60248201527f45524332303a206d696e7420746f20746865207a65726f206164647265737300604482015260640161060c565b610e0b60008383611275565b8060026000828254610e1d9190611890565b90915550506001600160a01b038216600081815260208181526040808320805486019055518481527fddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef910160405180910390a35050565b6001600160a01b038216610ed45760405162461bcd60e51b815260206004820152602160248201527f45524332303a206275726e2066726f6d20746865207a65726f206164647265736044820152607360f81b606482015260840161060c565b610ee082600083611275565b6001600160a01b03821660009081526020819052604090205481811015610f545760405162461bcd60e51b815260206004820152602260248201527f45524332303a206275726e20616d6f756e7420657863656564732062616c616e604482015261636560f01b606482015260840161060c565b6001600160a01b0383166000818152602081815260408083208686039055600280548790039055518581529192917fddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef910160405180910390a3505050565b60008060008411610ffe5760405162461bcd60e51b815260206004820152601660248201527504552433230536e617073686f743a20696420697320360541b604482015260640161060c565b6110066112d8565b8411156110555760405162461bcd60e51b815260206004820152601d60248201527f4552433230536e617073686f743a206e6f6e6578697374656e74206964000000604482015260640161060c565b600061106184866112e3565b845490915081036110795760008092509250506110a1565b6001846001018281548110611090576110906118a3565b906000526020600020015492509250505b9250929050565b600980546001600160a01b038381166001600160a01b0319831681179093556040519116919082907f8be0079c531659141344cd1fd0a4f28419497f9722a3daafe3b4186f6b6457e090600090a35050565b611102611390565b6009805460ff60a01b1916600160a01b1790557f62e78cea01bee320cd4e420270b5ea74000d11b0c9f74754ebdbfc544b05a258610d8c3390565b600061114d600880546001019055565b60006111576112d8565b90507f8030e83b04d87bef53480e26263266d6ca66863aa8506aca6f2559d18aa1cb678160405161118a91815260200190565b60405180910390a1919050565b6001600160a01b0381166000908152600a602052604090208054600181018255905b50919050565b600061041a6111cc610bd3565b8360405161190160f01b6020820152602281018390526042810182905260009060620160405160208183030381529060405280519060200120905092915050565b600080600061121e878787876113dd565b9150915061122b816114a1565b5095945050505050565b6001600160a01b038116600090815260056020908152604080832091839052909120546104a791906115eb565b6115eb565b610485600661126260025490565b61127d611390565b610854838383610835565b600954600160a01b900460ff166104855760405162461bcd60e51b815260206004820152601460248201527314185d5cd8589b194e881b9bdd081c185d5cd95960621b604482015260640161060c565b600061044e60085490565b815460009081036112f65750600061041a565b82546000905b808210156113435760006113108383611635565b6000878152602090209091508590820154111561132f5780915061133d565b61133a816001611890565b92505b506112fc565b60008211801561136f57508361136c8661135e6001866118b9565b600091825260209091200190565b54145b156113885761137f6001836118b9565b9250505061041a565b50905061041a565b600954600160a01b900460ff16156104855760405162461bcd60e51b815260206004820152601060248201526f14185d5cd8589b194e881c185d5cd95960821b604482015260640161060c565b6000807f7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a08311156114145750600090506003611498565b6040805160008082526020820180845289905260ff881692820192909252606081018690526080810185905260019060a0016020604051602081039080840390855afa158015611468573d6000803e3d6000fd5b5050604051601f1901519150506001600160a01b03811661149157600060019250925050611498565b9150600090505b94509492505050565b60008160048111156114b5576114b56118cc565b036114bd5750565b60018160048111156114d1576114d16118cc565b0361151e5760405162461bcd60e51b815260206004820152601860248201527f45434453413a20696e76616c6964207369676e61747572650000000000000000604482015260640161060c565b6002816004811115611532576115326118cc565b0361157f5760405162461bcd60e51b815260206004820152601f60248201527f45434453413a20696e76616c6964207369676e6174757265206c656e67746800604482015260640161060c565b6003816004811115611593576115936118cc565b036104a75760405162461bcd60e51b815260206004820152602260248201527f45434453413a20696e76616c6964207369676e6174757265202773272076616c604482015261756560f01b606482015260840161060c565b60006115f56112d8565b90508061160184611657565b1015610854578254600180820185556000858152602080822090930193909355938401805494850181558252902090910155565b600061164460028484186118e2565b61165090848416611890565b9392505050565b8054600090810361166a57506000919050565b8154829061167a906001906118b9565b8154811061168a5761168a6118a3565b90600052602060002001549050919050565b919050565b600060208083528351808285015260005b818110156116ce578581018301518582016040015282016116b2565b506000604082860101526040601f19601f8301168501019250505092915050565b80356001600160a01b038116811461169c57600080fd5b6000806040838503121561171957600080fd5b611722836116ef565b946020939093013593505050565b60008060006060848603121561174557600080fd5b61174e846116ef565b925061175c602085016116ef565b9150604084013590509250925092565b60006020828403121561177e57600080fd5b5035919050565b60006020828403121561179757600080fd5b611650826116ef565b600080600080600080600060e0888a0312156117bb57600080fd5b6117c4886116ef565b96506117d2602089016116ef565b95506040880135945060608801359350608088013560ff811681146117f657600080fd5b9699959850939692959460a0840135945060c09093013592915050565b6000806040838503121561182657600080fd5b61182f836116ef565b915061183d602084016116ef565b90509250929050565b600181811c9082168061185a57607f821691505b6020821081036111b957634e487b7160e01b600052602260045260246000fd5b634e487b7160e01b600052601160045260246000fd5b8082018082111561041a5761041a61187a565b634e487b7160e01b600052603260045260246000fd5b8181038181111561041a5761041a61187a565b634e487b7160e01b600052602160045260246000fd5b6000826118ff57634e487b7160e01b600052601260045260246000fd5b50049056fea26469706673582212208243706178a61a1cfcca24b8629ba2156ee35f315dbafcabb31f28aef8dcd28c64736f6c63430008120033
```
ContractABI:
```
[{"inputs":[],"stateMutability":"nonpayable","type":"constructor"},{"anonymous":false,"inputs":[{"indexed":true,"internalType":"address","name":"owner","type":"address"},{"indexed":true,"internalType":"address","name":"spender","type":"address"},{"indexed":false,"internalType":"uint256","name":"value","type":"uint256"}],"name":"Approval","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"internalType":"address","name":"previousOwner","type":"address"},{"indexed":true,"internalType":"address","name":"newOwner","type":"address"}],"name":"OwnershipTransferred","type":"event"},{"anonymous":false,"inputs":[{"indexed":false,"internalType":"address","name":"account","type":"address"}],"name":"Paused","type":"event"},{"anonymous":false,"inputs":[{"indexed":false,"internalType":"uint256","name":"id","type":"uint256"}],"name":"Snapshot","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"internalType":"address","name":"from","type":"address"},{"indexed":true,"internalType":"address","name":"to","type":"address"},{"indexed":false,"internalType":"uint256","name":"value","type":"uint256"}],"name":"Transfer","type":"event"},{"anonymous":false,"inputs":[{"indexed":false,"internalType":"address","name":"account","type":"address"}],"name":"Unpaused","type":"event"},{"inputs":[],"name":"DOMAIN_SEPARATOR","outputs":[{"internalType":"bytes32","name":"","type":"bytes32"}],"stateMutability":"view","type":"function"},{"inputs":[{"internalType":"address","name":"owner","type":"address"},{"internalType":"address","name":"spender","type":"address"}],"name":"allowance","outputs":[{"internalType":"uint256","name":"","type":"uint256"}],"stateMutability":"view","type":"function"},{"inputs":[{"internalType":"address","name":"spender","type":"address"},{"internalType":"uint256","name":"amount","type":"uint256"}],"name":"approve","outputs":[{"internalType":"bool","name":"","type":"bool"}],"stateMutability":"nonpayable","type":"function"},{"inputs":[{"internalType":"address","name":"account","type":"address"}],"name":"balanceOf","outputs":[{"internalType":"uint256","name":"","type":"uint256"}],"stateMutability":"view","type":"function"},{"inputs":[{"internalType":"address","name":"account","type":"address"},{"internalType":"uint256","name":"snapshotId","type":"uint256"}],"name":"balanceOfAt","outputs":[{"internalType":"uint256","name":"","type":"uint256"}],"stateMutability":"view","type":"function"},{"inputs":[{"internalType":"uint256","name":"amount","type":"uint256"}],"name":"burn","outputs":[],"stateMutability":"nonpayable","type":"function"},{"inputs":[{"internalType":"address","name":"account","type":"address"},{"internalType":"uint256","name":"amount","type":"uint256"}],"name":"burnFrom","outputs":[],"stateMutability":"nonpayable","type":"function"},{"inputs":[],"name":"decimals","outputs":[{"internalType":"uint8","name":"","type":"uint8"}],"stateMutability":"view","type":"function"},{"inputs":[{"internalType":"address","name":"spender","type":"address"},{"internalType":"uint256","name":"subtractedValue","type":"uint256"}],"name":"decreaseAllowance","outputs":[{"internalType":"bool","name":"","type":"bool"}],"stateMutability":"nonpayable","type":"function"},{"inputs":[{"internalType":"address","name":"spender","type":"address"},{"internalType":"uint256","name":"addedValue","type":"uint256"}],"name":"increaseAllowance","outputs":[{"internalType":"bool","name":"","type":"bool"}],"stateMutability":"nonpayable","type":"function"},{"inputs":[{"internalType":"address","name":"to","type":"address"},{"internalType":"uint256","name":"amount","type":"uint256"}],"name":"mint","outputs":[],"stateMutability":"nonpayable","type":"function"},{"inputs":[],"name":"name","outputs":[{"internalType":"string","name":"","type":"string"}],"stateMutability":"view","type":"function"},{"inputs":[{"internalType":"address","name":"owner","type":"address"}],"name":"nonces","outputs":[{"internalType":"uint256","name":"","type":"uint256"}],"stateMutability":"view","type":"function"},{"inputs":[],"name":"owner","outputs":[{"internalType":"address","name":"","type":"address"}],"stateMutability":"view","type":"function"},{"inputs":[],"name":"pause","outputs":[],"stateMutability":"nonpayable","type":"function"},{"inputs":[],"name":"paused","outputs":[{"internalType":"bool","name":"","type":"bool"}],"stateMutability":"view","type":"function"},{"inputs":[{"internalType":"address","name":"owner","type":"address"},{"internalType":"address","name":"spender","type":"address"},{"internalType":"uint256","name":"value","type":"uint256"},{"internalType":"uint256","name":"deadline","type":"uint256"},{"internalType":"uint8","name":"v","type":"uint8"},{"internalType":"bytes32","name":"r","type":"bytes32"},{"internalType":"bytes32","name":"s","type":"bytes32"}],"name":"permit","outputs":[],"stateMutability":"nonpayable","type":"function"},{"inputs":[],"name":"renounceOwnership","outputs":[],"stateMutability":"nonpayable","type":"function"},{"inputs":[],"name":"snapshot","outputs":[],"stateMutability":"nonpayable","type":"function"},{"inputs":[],"name":"symbol","outputs":[{"internalType":"string","name":"","type":"string"}],"stateMutability":"view","type":"function"},{"inputs":[],"name":"totalSupply","outputs":[{"internalType":"uint256","name":"","type":"uint256"}],"stateMutability":"view","type":"function"},{"inputs":[{"internalType":"uint256","name":"snapshotId","type":"uint256"}],"name":"totalSupplyAt","outputs":[{"internalType":"uint256","name":"","type":"uint256"}],"stateMutability":"view","type":"function"},{"inputs":[{"internalType":"address","name":"to","type":"address"},{"internalType":"uint256","name":"amount","type":"uint256"}],"name":"transfer","outputs":[{"internalType":"bool","name":"","type":"bool"}],"stateMutability":"nonpayable","type":"function"},{"inputs":[{"internalType":"address","name":"from","type":"address"},{"internalType":"address","name":"to","type":"address"},{"internalType":"uint256","name":"amount","type":"uint256"}],"name":"transferFrom","outputs":[{"internalType":"bool","name":"","type":"bool"}],"stateMutability":"nonpayable","type":"function"},{"inputs":[{"internalType":"address","name":"newOwner","type":"address"}],"name":"transferOwnership","outputs":[],"stateMutability":"nonpayable","type":"function"},{"inputs":[],"name":"unpause","outputs":[],"stateMutability":"nonpayable","type":"function"}]

```
Footer
© 2023 GitHub, Inc.
Footer navigation
[Terms](https://docs.github.com/site-policy/github-terms/github-terms-of-service)
[Privacy](https://docs.github.com/site-policy/privacy-policies/github-privacy-statement)
[Security](https://github.com/security)
[Status](https://www.githubstatus.com/)
[Docs](https://docs.github.com/)
[Contact GitHub](https://support.github.com/?tags=dotcom-footer)
[Pricing](https://github.com/pricing)
[API](https://docs.github.com/)
[Training](https://services.github.com/)
[Blog](https://github.blog/)
[About](https://github.com/about)

