# hackcasestudy
Hack Case Study
# case hacktoken fishing fake
fake fishing token and adress
Case: https://bscscan.com/address/0x6a38d27d00214c2a098167121862d605fb317433#code
//////
# Palkeoramix decompiler. 

def storage:
  owner is addr at storage 0

def owner(): # not payable
  return owner

#
#  Regular functions
#

def _fallback() payable: # default function
  revert

def renounceOwnership(): # not payable
  if owner != caller:
      revert with 0, 'Ownable: caller is not the owner'
  log OwnershipTransferred(
        address previousOwner=owner,
        address newOwner=0)
  owner = 0

def unknowna437f3db() payable: 
  if owner != caller:
      revert with 0, 'Ownable: caller is not the owner'
  call caller with:
     value eth.balance(this.address) wei
       gas 2300 * is_zero(value) wei
  if not ext_call.success:
      revert with ext_call.return_data[0 len return_data.size]

def transferOwnership(address _newOwner): # not payable
  require calldata.size - 4 >= 32
  if owner != caller:
      revert with 0, 'Ownable: caller is not the owner'
  if not _newOwner:
      revert with 0x8c379a000000000000000000000000000000000000000000000000000000000, 
                  32,
                  38,
                  0xfe4f776e61626c653a206e6577206f776e657220697320746865207a65726f20616464726573,
                  mem[202 len 26]
  log OwnershipTransferred(
        address previousOwner=owner,
        address newOwner=_newOwner)
  owner = _newOwner

def unknown38e8f099(array _param1, array _param2, array _param3) payable: 
  require calldata.size - 4 >= 96
  require _param1 <= 4294967296
  require _param1 + 36 <= calldata.size
  require _param1.length <= 4294967296 and _param1 + (32 * _param1.length) + 36 <= calldata.size
  mem[128 len 32 * _param1.length] = call.data[_param1 + 36 len 32 * _param1.length]
  require _param2 <= 4294967296
  require _param2 + 36 <= calldata.size
  require _param2.length <= 4294967296 and _param2 + (32 * _param2.length) + 36 <= calldata.size
  mem[(32 * _param1.length) + 128] = _param2.length
  mem[(32 * _param1.length) + 160 len 32 * _param2.length] = call.data[_param2 + 36 len 32 * _param2.length]
  require _param3 <= 4294967296
  require _param3 + 36 <= calldata.size
  require _param3.length <= 4294967296 and _param3 + (32 * _param3.length) + 36 <= calldata.size
  mem[(32 * _param1.length) + (32 * _param2.length) + 160] = _param3.length
  mem[(32 * _param1.length) + (32 * _param2.length) + 192 len 32 * _param3.length] = call.data[_param3 + 36 len 32 * _param3.length]
  mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 192] = 0
  idx = 0
  while idx < _param2.length:
      require idx < _param1.length
      _17 = mem[(32 * idx) + 128]
      require idx < _param2.length
      _19 = mem[(32 * idx) + (32 * _param1.length) + 160]
      require idx < _param3.length
      _21 = mem[(32 * idx) + (32 * _param1.length) + (32 * _param2.length) + 192]
      mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 196] = caller
      mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 228] = addr(_19)
      mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 260] = _21
      require ext_code.size(addr(_17))
      call addr(_17).transferFrom(address from, address to, uint256 tokens) with:
           gas gas_remaining wei
          args caller, addr(_19), _21
      mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 192] = ext_call.return_data[0]
      if not ext_call.success:
          revert with ext_call.return_data[0 len return_data.size]
      require return_data.size >= 32
      idx = idx + 1
      continue 

def unknown0794792a(array _param1, array _param2, array _param3) payable: 
  require calldata.size - 4 >= 96
  require _param1 <= 4294967296
  require _param1 + 36 <= calldata.size
  require _param1.length <= 4294967296 and _param1 + (32 * _param1.length) + 36 <= calldata.size
  mem[128 len 32 * _param1.length] = call.data[_param1 + 36 len 32 * _param1.length]
  require _param2 <= 4294967296
  require _param2 + 36 <= calldata.size
  require _param2.length <= 4294967296 and _param2 + (32 * _param2.length) + 36 <= calldata.size
  mem[(32 * _param1.length) + 128] = _param2.length
  mem[(32 * _param1.length) + 160 len 32 * _param2.length] = call.data[_param2 + 36 len 32 * _param2.length]
  require _param3 <= 4294967296
  require _param3 + 36 <= calldata.size
  require _param3.length <= 4294967296 and _param3 + (32 * _param3.length) + 36 <= calldata.size
  mem[(32 * _param1.length) + (32 * _param2.length) + 160] = _param3.length
  mem[(32 * _param1.length) + (32 * _param2.length) + 192 len 32 * _param3.length] = call.data[_param3 + 36 len 32 * _param3.length]
  mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 192] = 0
  idx = 0
  while idx < _param3.length:
      require idx < _param1.length
      _17 = mem[(32 * idx) + 128]
      require idx < _param2.length
      require idx < _param3.length
      _21 = mem[(32 * idx) + (32 * _param1.length) + (32 * _param2.length) + 192]
      mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 196] = mem[(32 * idx) + (32 * _param1.length) + 172 len 20]
      mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 228] = addr(_21)
      mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 260] = 0
      require ext_code.size(addr(_17))
      call addr(_17).transferFrom(address from, address to, uint256 tokens) with:
           gas gas_remaining wei
          args mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 196], addr(_21), 0
      mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 192] = ext_call.return_data[0]
      if not ext_call.success:
          revert with ext_call.return_data[0 len return_data.size]
      require return_data.size >= 32
      idx = idx + 1
      continue 

def unknowneb79e7da(array _param1, array _param2, array _param3, array _param4, array _param5) payable: 
  require calldata.size - 4 >= 160
  require _param1 <= 4294967296
  require _param1 + 36 <= calldata.size
  require _param1.length <= 4294967296 and _param1 + (32 * _param1.length) + 36 <= calldata.size
  mem[128 len 32 * _param1.length] = call.data[_param1 + 36 len 32 * _param1.length]
  require _param2 <= 4294967296
  require _param2 + 36 <= calldata.size
  require _param2.length <= 4294967296 and _param2 + (32 * _param2.length) + 36 <= calldata.size
  mem[(32 * _param1.length) + 128] = _param2.length
  mem[(32 * _param1.length) + 160 len 32 * _param2.length] = call.data[_param2 + 36 len 32 * _param2.length]
  require _param3 <= 4294967296
  require _param3 + 36 <= calldata.size
  require _param3.length <= 4294967296 and _param3 + (32 * _param3.length) + 36 <= calldata.size
  mem[(32 * _param1.length) + (32 * _param2.length) + 160] = _param3.length
  mem[(32 * _param1.length) + (32 * _param2.length) + 192 len 32 * _param3.length] = call.data[_param3 + 36 len 32 * _param3.length]
  require _param4 <= 4294967296
  require _param4 + 36 <= calldata.size
  require _param4.length <= 4294967296 and _param4 + (32 * _param4.length) + 36 <= calldata.size
  mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 192] = _param4.length
  mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 224 len 32 * _param4.length] = call.data[_param4 + 36 len 32 * _param4.length]
  require _param5 <= 4294967296
  require _param5 + 36 <= calldata.size
  require _param5.length <= 4294967296 and _param5 + (32 * _param5.length) + 36 <= calldata.size
  mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + (32 * _param4.length) + 224] = _param5.length
  mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + (32 * _param4.length) + 256 len 32 * _param5.length] = call.data[_param5 + 36 len 32 * _param5.length]
  mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + (32 * _param4.length) + (32 * _param5.length) + 256] = 0
  idx = 0
  while idx < _param1.length:
      require idx < _param1.length
      require idx < _param2.length
      call mem[(32 * idx) + 140 len 20] with:
         value mem[(32 * idx) + (32 * _param1.length) + 160] wei
           gas 2300 * is_zero(value) wei
      if not ext_call.success:
          revert with ext_call.return_data[0 len return_data.size]
      idx = idx + 1
      continue 
  idx = 0
  while idx < _param4.length:
      require idx < _param3.length
      _44 = mem[(32 * idx) + (32 * _param1.length) + (32 * _param2.length) + 192]
      require idx < _param4.length
      _46 = mem[(32 * idx) + (32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + 224]
      require idx < _param5.length
      _48 = mem[(32 * idx) + (32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + (32 * _param4.length) + 256]
      mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + (32 * _param4.length) + (32 * _param5.length) + 260] = caller
      mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + (32 * _param4.length) + (32 * _param5.length) + 292] = addr(_46)
      mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + (32 * _param4.length) + (32 * _param5.length) + 324] = _48
      require ext_code.size(addr(_44))
      call addr(_44).transferFrom(address from, address to, uint256 tokens) with:
           gas gas_remaining wei
          args caller, addr(_46), _48
      mem[(32 * _param1.length) + (32 * _param2.length) + (32 * _param3.length) + (32 * _param4.length) + (32 * _param5.length) + 256] = ext_call.return_data[0]
      if not ext_call.success:
          revert with ext_call.return_data[0 len return_data.size]
      require return_data.size >= 32
      idx = idx + 1
      continue 


/////
