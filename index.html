import React, { useState, useEffect, useRef } from 'react';

const CustomDropdown = ({ id, value, onChange, options, width, storage, onAddCustom, onRemove }) => {
  const [showDropdown, setShowDropdown] = useState(false);
  const [filteredOptions, setFilteredOptions] = useState([]);
  const [isMouseInDropdown, setIsMouseInDropdown] = useState(false);
  const inputRef = useRef(null);

  useEffect(() => {
    let allOptions = [...options];
    if (storage.customOptions[id]) {
      allOptions = [...new Set([...allOptions, ...storage.customOptions[id]])];
    }
    if (storage.optionsBlacklist[id]) {
      allOptions = allOptions.filter(opt => !storage.optionsBlacklist[id].includes(opt));
    }
    
    allOptions.sort((a, b) => {
      const aStartsWithNumber = /^\d/.test(a);
      const bStartsWithNumber = /^\d/.test(b);
      if (aStartsWithNumber && !bStartsWithNumber) return -1;
      if (!aStartsWithNumber && bStartsWithNumber) return 1;
      return a.localeCompare(b, 'de', { numeric: true, sensitivity: 'base' });
    });

    const searchValue = value.toLowerCase();
    const filtered = searchValue ? allOptions.filter(opt => opt.toLowerCase().startsWith(searchValue)) : allOptions;
    setFilteredOptions(filtered);
  }, [value, options, id, storage]);

  const handleSelect = (option) => {
    onChange(option);
    setShowDropdown(false);
  };

  const handleDelete = (option, e) => {
    e.stopPropagation();
    if (window.confirm(`Möchten Sie "${option}" wirklich löschen?`)) {
      onRemove(id, option);
      if (value === option) {
        onChange('');
      }
    }
  };

  const handleAddNew = () => {
    if (value && !options.includes(value)) {
      onAddCustom(id, value);
    }
    setShowDropdown(false);
  };

  return (
    <div style={{ position: 'relative', display: 'inline-block' }}>
      <input
        ref={inputRef}
        type="text"
        value={value}
        onChange={(e) => onChange(e.target.value)}
        onFocus={() => setShowDropdown(true)}
        onBlur={() => {
          setTimeout(() => {
            if (!isMouseInDropdown) setShowDropdown(false);
          }, 150);
        }}
        style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width }}
      />
      {showDropdown && (filteredOptions.length > 0 || value) && (
        <div
          onMouseEnter={() => setIsMouseInDropdown(true)}
          onMouseLeave={() => setIsMouseInDropdown(false)}
          style={{
            position: 'absolute',
            background: 'white',
            border: '1px solid #ccc',
            maxHeight: '200px',
            overflowY: 'auto',
            zIndex: 1000,
            boxShadow: '0 4px 6px rgba(0,0,0,0.1)',
            width
          }}
        >
          {filteredOptions.map((opt, idx) => (
            <div
              key={idx}
              style={{
                padding: '8px',
                cursor: 'pointer',
                borderBottom: '1px solid #eee',
                display: 'flex',
                justifyContent: 'space-between',
                alignItems: 'center'
              }}
            >
              <span
                onClick={() => handleSelect(opt)}
                style={{ flex: 1 }}
              >
                {opt}
              </span>
              <span
                onClick={(e) => handleDelete(opt, e)}
                style={{ cursor: 'pointer', padding: '0 5px', fontSize: '14px' }}
                title="Eintrag löschen"
              >
                🗑️
              </span>
            </div>
          ))}
          {value && !options.includes(value) && !filteredOptions.some(opt => opt.toLowerCase() === value.toLowerCase()) && (
            <div
              onClick={handleAddNew}
              style={{
                padding: '8px',
                cursor: 'pointer',
                borderTop: '2px solid #0056b3',
                fontWeight: 'bold',
                color: '#0056b3'
              }}
            >
              {value} (neu hinzufügen)
            </div>
          )}
        </div>
      )}
    </div>
  );
};

const KoiDatasheet = () => {
  // State für alle Felder
  const [fotosNum, setFotosNum] = useState('');
  const [inputDate, setInputDate] = useState('');
  const [howToGet, setHowToGet] = useState('Tour KZ');
  const [breeder, setBreeder] = useState('');
  const [agents, setAgents] = useState({ YI: true, KZ: false, CC: false });
  const [descPrefixes, setDescPrefixes] = useState({ Ginrin: false, Doitsu: false, Tancho: false, Maruten: false });
  const [description, setDescription] = useState('');
  const [qty, setQty] = useState('1');
  const [oya, setOya] = useState('');
  const [ageFrom, setAgeFrom] = useState('2');
  const [ageTo, setAgeTo] = useState('');
  const [sex, setSex] = useState('w');
  const [sizeFrom, setSizeFrom] = useState('');
  const [sizeTo, setSizeTo] = useState('');
  const [bprice, setBprice] = useState('');
  const [bpricePercent, setBpricePercent] = useState(false);
  const [kprice, setKprice] = useState('');
  const [kunde, setKunde] = useState('KZ');
  const [kundeOther, setKundeOther] = useState('');
  const [kundeSub, setKundeSub] = useState(false);
  const [subValue, setSubValue] = useState('');
  const [bemerkungen, setBemerkungen] = useState('');
  const [azukariCheck, setAzukariCheck] = useState(false);
  const [azukariValue, setAzukariValue] = useState('');
  const [azukariType, setAzukariType] = useState('');
  const [koiShowCheck, setKoiShowCheck] = useState(false);
  const [koiShowAJKS, setKoiShowAJKS] = useState(false);
  const [koiShowAJYKS, setKoiShowAJYKS] = useState(false);
  const [koiShowAndere, setKoiShowAndere] = useState(false);
  const [koiShowAndereText, setKoiShowAndereText] = useState('');
  const [gebuehrCheck, setGebuehrCheck] = useState(false);
  const [gebuehrValue, setGebuehrValue] = useState('');
  const [gebuehrType, setGebuehrType] = useState('');
  const [additionalGebuehr, setAdditionalGebuehr] = useState([]);
  const [successMsg, setSuccessMsg] = useState(false);

  // Storage State
  const [storage, setStorage] = useState({
    customOptions: {},
    optionsBlacklist: {},
    usedFotoNumbers: [],
    koiDefaults: null
  });

  const priceMap = {
    '1': 'i', '2': 'f', '3': 's', '4': 'y', '5': 'g',
    '6': 'r', '7': 'n', '8': 'h', '9': 'k',
    '00': '2', '000': 't', '0000': 'z', '00000': '5', '000000': 'm'
  };

  const dropdownOptions = {
    howToGet: ['Tour KZ', 'CC Tour', 'Online Auktion', 'Narita web-auction', 'Live Auktion'],
    breeder: ['Aoki', 'Beppu', 'Dainichi', 'Dainichi (T)', 'Genjiro', 'Higashi', 'Hiroi', 'Hoshikin', 'Hosokai', 'Igarashi', 'Ikarashi', 'Isa', 'Ishihara', 'Izumiya', 'Kanno', 'Kawakami', 'Kibi', 'KK Sakai', 'Kondo', 'Konishi', 'Maruhide', 'Maruju', 'Marusaka', 'Marusei', 'Matsue', 'Momotaro', 'Murata', 'Nagoshi', 'Narita', 'Nogami', 'Odakan', 'Ofuchi', 'Oishi', 'Omosako', 'Otsuka', 'Oyama', 'Sakai FF', 'Sakazume', 'Sekiguchi', 'Shinoda', 'Takigawa', 'Tamaura', 'Taniguchi', 'Torazo'],
    oya: ['Super Butta', 'Kinsen x Nao', 'Masako x Pandora', 'Futaba x Pandora', 'Red Card x Pandora', 'Silk Sonic', 'Miss Kyoto'],
    description: ['2sai selected', '2-3sai selected', '3sai selected', 'Ai Goromo', 'Aka', 'Aka Matsuba', 'Asagi', 'Bekko', 'Beni', 'Beni Kikokuryu', 'Beni Kumonryu', 'Benigoi', 'Bigscale', 'Chagoi', 'Goshiki', 'Hi', 'Hi Utsuri', 'Ki', 'Kin', 'Kin Showa', 'Kindai', 'Kohaku', 'Kujaku', 'Ochiba', 'Platinum', 'Sanke', 'Shiro Utsuri', 'Showa', 'Shusui', 'Soragoi', 'Utsuri', 'Yamabuki'],
    sub: ['Armbrust', 'Essel']
  };

  useEffect(() => {
    const now = new Date();
    const dateStr = now.toISOString().slice(2, 10).replace(/-/g, '');
    setInputDate(dateStr);
  }, []);

  // Berechne Anzahl der zusätzlichen Gebühr-Felder
  useEffect(() => {
    let count = 0;
    if (koiShowAJKS) count++;
    if (koiShowAJYKS) count++;
    if (koiShowAndere) count++;
    
    const newAdditional = [];
    for (let i = 2; i <= count; i++) {
      const existing = additionalGebuehr.find(g => g.index === i);
      newAdditional.push(existing || { index: i, check: false, value: '', type: '' });
    }
    setAdditionalGebuehr(newAdditional);
  }, [koiShowAJKS, koiShowAJYKS, koiShowAndere]);

  const encodePrice = (price) => {
    if (!price || price === '0' || price === '') return '';
    const cleaned = price.toString().replace(/\D/g, '');
    if (!cleaned) return '';
    
    let remaining = cleaned;
    let encoded = '';
    const patterns = [
      ['000000', 'm'], ['00000', '5'], ['0000', 'z'], ['000', 't'], ['00', '2']
    ];
    
    while (remaining.length > 0) {
      let replaced = false;
      for (const [pattern, code] of patterns) {
        if (remaining.startsWith(pattern)) {
          encoded += code;
          remaining = remaining.substring(pattern.length);
          replaced = true;
          break;
        }
      }
      if (!replaced) {
        const char = remaining[0];
        encoded += priceMap[char] || '0';
        remaining = remaining.substring(1);
      }
    }
    return encoded;
  };

  const handleFotoBlur = () => {
    if (!fotosNum) return;
    
    const paddedValue = fotosNum.padStart(3, '0');
    
    if (storage.usedFotoNumbers.includes(paddedValue)) {
      let nextNumber = parseInt(paddedValue) + 1;
      
      while (storage.usedFotoNumbers.includes(nextNumber.toString().padStart(3, '0')) && nextNumber < 1000) {
        nextNumber++;
      }
      
      if (nextNumber >= 1000) {
        alert('⚠️ Alle Foto-Nummern sind bereits verwendet!');
        setFotosNum(paddedValue);
        return;
      }
      
      const nextPadded = nextNumber.toString().padStart(3, '0');
      
      if (window.confirm(`Foto-Nummer ${paddedValue} wurde bereits verwendet!\n\nMöchten Sie die nächste freie Nummer ${nextPadded} verwenden?`)) {
        setFotosNum(nextPadded);
      } else {
        setFotosNum(paddedValue);
      }
    } else {
      setFotosNum(paddedValue);
    }
  };

  const saveFotoNumber = (number) => {
    if (!number || storage.usedFotoNumbers.includes(number)) return;
    setStorage(prev => ({
      ...prev,
      usedFotoNumbers: [...prev.usedFotoNumbers, number]
    }));
  };

  const addCustomOption = (fieldId, value) => {
    if (!value) return;
    setStorage(prev => {
      const customOptions = { ...prev.customOptions };
      if (!customOptions[fieldId]) customOptions[fieldId] = [];
      if (!customOptions[fieldId].includes(value)) {
        customOptions[fieldId].push(value);
      }
      return { ...prev, customOptions };
    });
  };

  const removeOption = (fieldId, value) => {
    if (!value) return;
    setStorage(prev => {
      const customOptions = { ...prev.customOptions };
      if (customOptions[fieldId]) {
        customOptions[fieldId] = customOptions[fieldId].filter(opt => opt !== value);
      }
      
      const blacklist = { ...prev.optionsBlacklist };
      if (!blacklist[fieldId]) blacklist[fieldId] = [];
      if (!blacklist[fieldId].includes(value)) {
        blacklist[fieldId].push(value);
      }
      
      return { ...prev, customOptions, optionsBlacklist: blacklist };
    });
  };

  const getAgentValue = () => {
    const checked = [];
    if (agents.KZ) checked.push('KZ');
    if (agents.CC) checked.push('CC');
    if (agents.YI) checked.push('YI');
    
    if (checked.length === 2) {
      const first = checked.find(v => v !== 'YI');
      return `${first}-YI`;
    }
    return checked.join(',');
  };

  const getDescriptionWithPrefix = () => {
    const prefixes = Object.keys(descPrefixes).filter(k => descPrefixes[k]);
    if (prefixes.length > 0 && description) {
      return prefixes.join(' ') + ' ' + description;
    }
    return description;
  };

  const getAgeValue = () => {
    if (ageFrom && ageTo) return `${ageFrom}-${ageTo}`;
    else if (ageFrom) return ageFrom;
    else if (ageTo) return ageTo;
    return '';
  };

  const getSizeValue = () => {
    if (sizeFrom && sizeTo) return `${sizeFrom}-${sizeTo}`;
    else if (sizeFrom) return sizeFrom;
    else if (sizeTo) return sizeTo;
    return '';
  };

  const getKundeValue = () => {
    if (kunde === 'Andere') return kundeOther;
    return kunde;
  };

  const getTitle = () => {
    const fotosComplete = '26-' + fotosNum;
    let bpriceEncoded = encodePrice(bprice);
    const kpriceEncoded = encodePrice(kprice);
    
    if (bpricePercent) {
      bpriceEncoded += '+%X';
    }
    
    const parts = [
      fotosComplete,
      inputDate,
      howToGet,
      breeder,
      getAgentValue(),
      getDescriptionWithPrefix(),
      qty,
      oya || '',
      getAgeValue(),
      sex,
      getSizeValue(),
      bpriceEncoded,
      kpriceEncoded,
      getKundeValue()
    ];
    
    return parts.join(', ');
  };

  const getBody = () => {
    const parts = [];
    
    if (kundeSub && subValue) {
      parts.push(`Kunde: ${subValue}`);
    }
    
    if (azukariCheck) {
      const currentYear = new Date().getFullYear();
      const nextYear = (currentYear + 1) % 100;
      
      const extras = [];
      if (azukariValue) {
        const encoded = encodePrice(azukariValue);
        extras.push(encoded);
      }
      if (azukariType) {
        extras.push(azukariType);
      }
      
      if (extras.length > 0) {
        parts.push(`Azukari${nextYear} (${extras.join(', ')})`);
      } else {
        parts.push(`Azukari${nextYear}`);
      }
    }
    
    const koiShowOptions = [];
    if (koiShowAJKS) koiShowOptions.push('AJKS');
    if (koiShowAJYKS) koiShowOptions.push('AJYKS');
    if (koiShowAndere) {
      koiShowOptions.push(koiShowAndereText || 'Andere');
    }
    
    const currentYear = new Date().getFullYear();
    const nextYear = (currentYear + 1) % 100;
    
    if (gebuehrCheck && koiShowOptions.length > 0) {
      const gebuehrExtras = [];
      if (gebuehrValue) {
        const encoded = encodePrice(gebuehrValue);
        gebuehrExtras.push(encoded);
      }
      if (gebuehrType) {
        gebuehrExtras.push(gebuehrType);
      }
      
      const showName = koiShowOptions[0];
      if (gebuehrExtras.length > 0) {
        parts.push(`${showName}${nextYear} (${gebuehrExtras.join(', ')})`);
      } else {
        parts.push(`${showName}${nextYear}`);
      }
    }
    
    additionalGebuehr.forEach((gebuehr, idx) => {
      const showIndex = idx + 1;
      if (gebuehr.check && koiShowOptions[showIndex]) {
        const gebuehrExtras = [];
        if (gebuehr.value) {
          const encoded = encodePrice(gebuehr.value);
          gebuehrExtras.push(encoded);
        }
        if (gebuehr.type) {
          gebuehrExtras.push(gebuehr.type);
        }
        
        const showName = koiShowOptions[showIndex];
        if (gebuehrExtras.length > 0) {
          parts.push(`${showName}${nextYear} (${gebuehrExtras.join(', ')})`);
        } else {
          parts.push(`${showName}${nextYear}`);
        }
      }
    });
    
    if (bemerkungen) {
      parts.push(bemerkungen);
    }
    
    return parts.join('\n');
  };

  const handleAgentChange = (agentName) => {
    const newAgents = { ...agents, [agentName]: !agents[agentName] };
    
    const checked = Object.keys(newAgents).filter(k => newAgents[k]);
    if (checked.length > 2) return;
    if (newAgents.KZ && newAgents.CC) return;
    
    setAgents(newAgents);
  };

  const copyTitle = () => {
    const title = getTitle();
    navigator.clipboard.writeText(title).then(() => {
      setSuccessMsg(true);
      setTimeout(() => setSuccessMsg(false), 3000);
    }).catch(() => {
      alert('Kopieren fehlgeschlagen.');
    });
  };

  const copyBody = () => {
    const body = getBody();
    if (!body) {
      alert('Kein Notizinhalt vorhanden.');
      return;
    }
    navigator.clipboard.writeText(body).then(() => {
      setSuccessMsg(true);
      setTimeout(() => setSuccessMsg(false), 3000);
    }).catch(() => {
      alert('Kopieren fehlgeschlagen.');
    });
  };

  const sendToKeep = () => {
    if (fotosNum) {
      saveFotoNumber(fotosNum);
    }
    
    ['howToGet', 'breeder', 'oya', 'description', 'sub'].forEach(fieldId => {
      const valueMap = { howToGet, breeder, oya, description, sub: subValue };
      const value = valueMap[fieldId];
      if (value && !dropdownOptions[fieldId]?.includes(value)) {
        addCustomOption(fieldId, value);
      }
    });
    
    copyTitle();
    setTimeout(() => {
      window.open('https://keep.google.com', '_blank');
    }, 500);
  };

  const resetForm = () => {
    setFotosNum('');
    const now = new Date();
    setInputDate(now.toISOString().slice(2, 10).replace(/-/g, ''));
    setHowToGet('Tour KZ');
    setBreeder('');
    setAgents({ YI: true, KZ: false, CC: false });
    setDescPrefixes({ Ginrin: false, Doitsu: false, Tancho: false, Maruten: false });
    setDescription('');
    setQty('1');
    setOya('');
    setAgeFrom('2');
    setAgeTo('');
    setSex('w');
    setSizeFrom('');
    setSizeTo('');
    setBprice('');
    setBpricePercent(false);
    setKprice('');
    setKunde('');
    setKundeOther('');
    setKundeSub(false);
    setSubValue('');
    setBemerkungen('');
    setAzukariCheck(false);
    setAzukariValue('');
    setAzukariType('');
    setKoiShowCheck(false);
    setKoiShowAJKS(false);
    setKoiShowAJYKS(false);
    setKoiShowAndere(false);
    setKoiShowAndereText('');
    setGebuehrCheck(false);
    setGebuehrValue('');
    setGebuehrType('');
    setAdditionalGebuehr([]);
  };

  const titleText = getTitle();
  const bodyText = getBody();
  const titleEmpty = !titleText || titleText === '26-, , , , YI, , 1, , , w, , , , ';
  const bodyEmpty = !bodyText;

  return (
    <div style={{ fontFamily: 'Arial, sans-serif', margin: '10px', background: '#f8f9fa', color: '#333', fontSize: '14px' }}>
      <h2 style={{ textAlign: 'center', fontSize: '18px' }}>🐟 Koi Datenblatt</h2>

      <div>
        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold', fontSize: '14px' }}>Fotos:</label>
        <div style={{ display: 'inline-block' }}>
          <span style={{ fontWeight: 'bold', fontSize: '18px', marginRight: '5px', color: '#0056b3' }}>26-</span>
          <input 
            type="text" 
            value={fotosNum}
            onChange={(e) => setFotosNum(e.target.value.replace(/\D/g, '').slice(0, 3))}
            onBlur={handleFotoBlur}
            placeholder="000"
            maxLength="3"
            style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '70px' }}
          />
        </div>
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold' }}>Input Date:</label>
        <input 
          type="text"
          value={inputDate}
          onChange={(e) => setInputDate(e.target.value)}
          placeholder="YYMMDD"
          maxLength="6"
          style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '120px' }}
        />
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold' }}>How to Get:</label>
        <CustomDropdown
          id="howToGet"
          value={howToGet}
          onChange={setHowToGet}
          options={dropdownOptions.howToGet}
          width="160px"
          storage={storage}
          onAddCustom={addCustomOption}
          onRemove={removeOption}
        />
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold' }}>Breeder:</label>
        <CustomDropdown
          id="breeder"
          value={breeder}
          onChange={setBreeder}
          options={dropdownOptions.breeder}
          width="120px"
          storage={storage}
          onAddCustom={addCustomOption}
          onRemove={removeOption}
        />
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold' }}>Agent:</label>
        <span style={{ display: 'inline-block' }}>
          <label style={{ width: 'auto', marginRight: '8px', fontSize: '14px' }}>
            <input type="checkbox" checked={agents.YI} onChange={() => handleAgentChange('YI')} /> YI
          </label>
          <label style={{ width: 'auto', marginRight: '8px', fontSize: '14px' }}>
            <input type="checkbox" checked={agents.KZ} onChange={() => handleAgentChange('KZ')} /> KZ
          </label>
          <label style={{ width: 'auto', marginRight: '8px', fontSize: '14px' }}>
            <input type="checkbox" checked={agents.CC} onChange={() => handleAgentChange('CC')} /> CC
          </label>
        </span>
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold', verticalAlign: 'top' }}>Description:</label>
        <div style={{ display: 'inline-block', verticalAlign: 'top' }}>
          <div>
            <label style={{ width: 'auto', marginRight: '8px', fontSize: '14px' }}>
              <input type="checkbox" checked={descPrefixes.Ginrin} onChange={() => setDescPrefixes({...descPrefixes, Ginrin: !descPrefixes.Ginrin})} /> Ginrin
            </label>
            <label style={{ width: 'auto', marginRight: '8px', fontSize: '14px' }}>
              <input type="checkbox" checked={descPrefixes.Doitsu} onChange={() => setDescPrefixes({...descPrefixes, Doitsu: !descPrefixes.Doitsu})} /> Doitsu
            </label>
          </div>
          <div>
            <label style={{ width: 'auto', marginRight: '8px', fontSize: '14px' }}>
              <input type="checkbox" checked={descPrefixes.Tancho} onChange={() => setDescPrefixes({...descPrefixes, Tancho: !descPrefixes.Tancho})} /> Tancho
            </label>
            <label style={{ width: 'auto', marginRight: '8px', fontSize: '14px' }}>
              <input type="checkbox" checked={descPrefixes.Maruten} onChange={() => setDescPrefixes({...descPrefixes, Maruten: !descPrefixes.Maruten})} /> Maruten
            </label>
          </div>
          <CustomDropdown
            id="description"
            value={description}
            onChange={setDescription}
            options={dropdownOptions.description}
            width="140px"
            storage={storage}
            onAddCustom={addCustomOption}
            onRemove={removeOption}
          />
        </div>
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold' }}>Qty:</label>
        <input 
          type="text"
          value={qty}
          onChange={(e) => setQty(e.target.value.replace(/\D/g, '').slice(0, 3))}
          style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '70px' }}
        />
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold' }}>Oya:</label>
        <CustomDropdown
          id="oya"
          value={oya}
          onChange={setOya}
          options={dropdownOptions.oya}
          width="160px"
          storage={storage}
          onAddCustom={addCustomOption}
          onRemove={removeOption}
        />
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold' }}>Age:</label>
        <input 
          type="text"
          value={ageFrom}
          onChange={(e) => setAgeFrom(e.target.value.slice(0, 2))}
          style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '50px' }}
        />
        <span style={{ margin: '0 5px' }}>-</span>
        <input 
          type="text"
          value={ageTo}
          onChange={(e) => setAgeTo(e.target.value.slice(0, 2))}
          style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '50px' }}
        />
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold' }}>Sex:</label>
        <span style={{ display: 'inline-block' }}>
          <label style={{ width: 'auto', marginRight: '8px', fontSize: '14px' }}>
            <input type="radio" checked={sex === 'm'} onChange={() => setSex('m')} /> m
          </label>
          <label style={{ width: 'auto', marginRight: '8px', fontSize: '14px' }}>
            <input type="radio" checked={sex === 'mw'} onChange={() => setSex('mw')} /> mw
          </label>
          <label style={{ width: 'auto', marginRight: '8px', fontSize: '14px' }}>
            <input type="radio" checked={sex === 'w'} onChange={() => setSex('w')} /> w
          </label>
        </span>
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold' }}>Size/cm:</label>
        <input 
          type="text"
          value={sizeFrom}
          onChange={(e) => setSizeFrom(e.target.value.replace(/\D/g, '').slice(0, 3))}
          style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '70px' }}
        />
        <span style={{ margin: '0 5px' }}>-</span>
        <input 
          type="text"
          value={sizeTo}
          onChange={(e) => setSizeTo(e.target.value.replace(/\D/g, '').slice(0, 3))}
          style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '70px' }}
        />
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold' }}>B.Price:</label>
        <input 
          type="text"
          value={bprice}
          onChange={(e) => setBprice(e.target.value.replace(/\D/g, '').slice(0, 7))}
          style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '140px' }}
        />
        <label style={{ marginLeft: '10px', width: 'auto' }}>
          <input type="checkbox" checked={bpricePercent} onChange={() => setBpricePercent(!bpricePercent)} /> +%X
        </label>
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold' }}>K.Price:</label>
        <input 
          type="text"
          value={kprice}
          onChange={(e) => setKprice(e.target.value.replace(/\D/g, '').slice(0, 7))}
          style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '140px' }}
        />
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold' }}>Kunde:</label>
        <span style={{ display: 'inline-block' }}>
          <label style={{ width: 'auto', marginRight: '8px', fontSize: '14px' }}>
            <input type="radio" checked={kunde === 'KZ'} onChange={() => setKunde('KZ')} /> KZ
          </label>
          <label style={{ width: 'auto', marginRight: '8px', fontSize: '14px' }}>
            <input type="radio" checked={kunde === 'CC'} onChange={() => setKunde('CC')} /> CC
          </label>
          <label style={{ width: 'auto', marginRight: '8px', fontSize: '14px' }}>
            <input type="radio" checked={kunde === 'Andere'} onChange={() => setKunde('Andere')} /> Andere
          </label>
        </span>
        {kunde === 'Andere' && (
          <input 
            type="text"
            value={kundeOther}
            onChange={(e) => setKundeOther(e.target.value)}
            style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '100px', marginLeft: '5px' }}
            maxLength="50"
          />
        )}
        <span style={{ display: 'inline-block', marginLeft: '10px' }}>
          <label style={{ width: 'auto' }}>
            <input type="checkbox" checked={kundeSub} onChange={() => setKundeSub(!kundeSub)} /> Sub:
          </label>
        </span>
        {kundeSub && (
          <CustomDropdown
            id="sub"
            value={subValue}
            onChange={setSubValue}
            options={dropdownOptions.sub}
            width="100px"
            storage={storage}
            onAddCustom={addCustomOption}
            onRemove={removeOption}
          />
        )}
        <br />

        <label style={{ display: 'inline-block', width: '110px', marginTop: '10px', fontWeight: 'bold' }}>Bemerkungen:</label>
        <input 
          type="text"
          value={bemerkungen}
          onChange={(e) => setBemerkungen(e.target.value)}
          style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '160px' }}
        />
        <div style={{ marginTop: '5px' }}>
          <label style={{ width: 'auto' }}>
            <input type="checkbox" checked={azukariCheck} onChange={() => setAzukariCheck(!azukariCheck)} /> Azukari:
          </label>
          {azukariCheck && (
            <>
              <input 
                type="text"
                value={azukariValue}
                onChange={(e) => setAzukariValue(e.target.value.replace(/\D/g, '').slice(0, 6))}
                style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '80px', marginLeft: '5px' }}
              />
              <label style={{ marginLeft: '10px' }}>
                <input type="radio" checked={azukariType === 'komi'} onChange={() => setAzukariType('komi')} /> komi
              </label>
              <label>
                <input type="radio" checked={azukariType === 'komic'} onChange={() => setAzukariType('komic')} /> komic
              </label>
            </>
          )}
        </div>

        <div style={{ marginTop: '10px' }}>
          <label style={{ width: 'auto' }}>
            <input type="checkbox" checked={koiShowCheck} onChange={() => setKoiShowCheck(!koiShowCheck)} /> Koi-Show:
          </label>
          {koiShowCheck && (
            <div style={{ display: 'inline-block', marginLeft: '10px' }}>
              <label><input type="checkbox" checked={koiShowAJKS} onChange={() => setKoiShowAJKS(!koiShowAJKS)} /> AJKS</label>
              <label><input type="checkbox" checked={koiShowAJYKS} onChange={() => setKoiShowAJYKS(!koiShowAJYKS)} /> AJYKS</label>
              <label><input type="checkbox" checked={koiShowAndere} onChange={() => setKoiShowAndere(!koiShowAndere)} /> Andere:</label>
              {koiShowAndere && (
                <input 
                  type="text"
                  value={koiShowAndereText}
                  onChange={(e) => setKoiShowAndereText(e.target.value)}
                  style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '80px', marginLeft: '5px' }}
                  maxLength="50"
                />
              )}
            </div>
          )}
        </div>

        {koiShowCheck && (
          <div style={{ marginTop: '10px' }}>
            <label style={{ width: 'auto' }}>
              <input type="checkbox" checked={gebuehrCheck} onChange={() => setGebuehrCheck(!gebuehrCheck)} /> Gebühr:
            </label>
            {gebuehrCheck && (
              <>
                <input 
                  type="text"
                  value={gebuehrValue}
                  onChange={(e) => setGebuehrValue(e.target.value.replace(/\D/g, '').slice(0, 7))}
                  style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '80px', marginLeft: '5px' }}
                />
                <label style={{ marginLeft: '10px' }}>
                  <input type="radio" checked={gebuehrType === 'komi'} onChange={() => setGebuehrType('komi')} /> komi
                </label>
                <label>
                  <input type="radio" checked={gebuehrType === 'komic'} onChange={() => setGebuehrType('komic')} /> komic
                </label>
              </>
            )}
          </div>
        )}

        {additionalGebuehr.map((gebuehr, idx) => (
          <div key={idx} style={{ marginTop: '10px' }}>
            <label style={{ width: 'auto' }}>
              <input 
                type="checkbox" 
                checked={gebuehr.check} 
                onChange={() => {
                  const newAdditional = [...additionalGebuehr];
                  newAdditional[idx].check = !gebuehr.check;
                  setAdditionalGebuehr(newAdditional);
                }} 
              /> Gebühr:
            </label>
            {gebuehr.check && (
              <>
                <input 
                  type="text"
                  value={gebuehr.value}
                  onChange={(e) => {
                    const newAdditional = [...additionalGebuehr];
                    newAdditional[idx].value = e.target.value.replace(/\D/g, '').slice(0, 7);
                    setAdditionalGebuehr(newAdditional);
                  }}
                  style={{ padding: '6px', border: '1px solid #ccc', borderRadius: '4px', fontSize: '14px', width: '80px', marginLeft: '5px' }}
                />
                <label style={{ marginLeft: '10px' }}>
                  <input 
                    type="radio" 
                    checked={gebuehr.type === 'komi'} 
                    onChange={() => {
                      const newAdditional = [...additionalGebuehr];
                      newAdditional[idx].type = 'komi';
                      setAdditionalGebuehr(newAdditional);
                    }} 
                  /> komi
                </label>
                <label>
                  <input 
                    type="radio" 
                    checked={gebuehr.type === 'komic'} 
                    onChange={() => {
                      const newAdditional = [...additionalGebuehr];
                      newAdditional[idx].type = 'komic';
                      setAdditionalGebuehr(newAdditional);
                    }} 
                  /> komic
                </label>
              </>
            )}
          </div>
        ))}

        <div style={{ marginTop: '20px', padding: '15px', background: '#fff', borderRadius: '6px', border: '2px solid #0056b3' }}>
          <h3 style={{ margin: '0 0 10px 0', color: '#0056b3', fontSize: '14px' }}>📝 Vorschau Google Keep Notiz:</h3>
          <div>
            <strong style={{ fontSize: '12px', color: '#666' }}>Titel:</strong>
            <div style={{ padding: '12px', background: '#e7f3ff', borderRadius: '4px', fontWeight: 'bold', color: '#0056b3', wordBreak: 'break-word', fontSize: '13px', marginBottom: '10px', minHeight: '20px' }}>
              {titleEmpty ? <span style={{ color: '#999', fontStyle: 'italic' }}>Titel wird hier angezeigt...</span> : titleText}
            </div>
          </div>
          <div>
            <strong style={{ fontSize: '12px', color: '#666' }}>Notizinhalt:</strong>
            <div style={{ padding: '12px', background: '#f8f9fa', borderRadius: '4px', wordBreak: 'break-word', fontSize: '13px', whiteSpace: 'pre-wrap', minHeight: '40px', color: '#333', border: '1px solid #dee2e6' }}>
              {bodyEmpty ? <span style={{ color: '#999', fontStyle: 'italic' }}>Notizinhalt wird hier angezeigt...</span> : bodyText}
            </div>
          </div>
        </div>

        {successMsg && (
          <div style={{ color: '#28a745', marginTop: '10px', padding: '10px', background: '#d4edda', borderRadius: '4px', textAlign: 'center' }}>
            ✅ Text kopiert!
          </div>
        )}

        <button onClick={sendToKeep} style={{ marginTop: '20px', padding: '10px 16px', background: '#0056b3', color: 'white', border: 'none', borderRadius: '6px', cursor: 'pointer', fontSize: '14px', width: '100%' }}>
          📋 Titel kopieren & Keep öffnen
        </button>

        <div style={{ display: 'flex', gap: '10px', marginTop: '10px' }}>
          <button onClick={copyTitle} style={{ padding: '10px 16px', background: '#17a2b8', color: 'white', border: 'none', borderRadius: '6px', cursor: 'pointer', fontSize: '14px', flex: 1 }}>
            📄 Nur Titel kopieren
          </button>
          <button onClick={copyBody} style={{ padding: '10px 16px', background: '#28a745', color: 'white', border: 'none', borderRadius: '6px', cursor: 'pointer', fontSize: '14px', flex: 1 }}>
            📝 Nur Notizinhalt kopieren
          </button>
        </div>

        <button onClick={resetForm} style={{ marginTop: '10px', padding: '10px 16px', background: '#6c757d', color: 'white', border: 'none', borderRadius: '6px', cursor: 'pointer', fontSize: '14px', width: '100%' }}>
          🧹 Zurücksetzen
        </button>

        <div style={{ background: '#fff3cd', padding: '15px', borderRadius: '6px', marginTop: '20px', borderLeft: '4px solid #ffc107' }}>
          <h3 style={{ marginTop: 0, color: '#856404' }}>📌 So verwenden Sie das Formular:</h3>
          
          <h4 style={{ color: '#856404', marginBottom: '5px' }}>Methode 1: Schnell (nur Titel)</h4>
          <ol>
            <li>Füllen Sie alle Felder aus</li>
            <li>Klicken Sie auf "📋 Titel kopieren & Keep öffnen"</li>
            <li>In Keep: Neue Notiz (+) → Im <strong>Notiz-Bereich</strong> einfügen</li>
          </ol>

          <h4 style={{ color: '#856404', marginBottom: '5px' }}>Methode 2: Komplett (Titel + Notizinhalt getrennt)</h4>
          <ol>
            <li>Füllen Sie alle Felder aus</li>
            <li>Klicken Sie auf "📄 Nur Titel kopieren"</li>
            <li>Öffnen Sie Google Keep → Neue Notiz (+)</li>
            <li>Klicken Sie auf den <strong>Titel-Bereich</strong> (oben, wo "Titel" steht)</li>
            <li>Einfügen (lange drücken → Einfügen)</li>
            <li>Zurück zum Formular → "📝 Nur Notizinhalt kopieren"</li>
            <li>In Keep: In den <strong>Notiz-Bereich</strong> (unten) klicken</li>
            <li>Einfügen</li>
          </ol>
          
          <p><strong>💡 Features:</strong></p>
          <ul>
            <li>Dropdown-Menüs mit Autovervollständigung</li>
            <li>Neue Einträge können direkt hinzugefügt werden</li>
            <li>Einträge können mit 🗑️ gelöscht werden</li>
            <li>Foto-Nummern werden automatisch geprüft und formatiert</li>
            <li>Titel und Notizinhalt sind klar getrennt</li>
            <li><strong>Kunde ist standardmäßig auf KZ gesetzt</strong></li>
          </ul>
        </div>
      </div>
    </div>
  );
};

export default KoiDatasheet;