# pasatya277

 
 import React,{useState,useEffect} from 'react';
 import axios from 'axios';


 const Myitem=()=>{
    const[itemlist,updateitem]=useState([]);

    axios.get('item.json')
    .then(response=>{
        updateitem(response.data)
    })
    return(
        <div>
            <h1>Data Display</h1>
            <table  cellpadding='18' className='form-control offset-3 table-bordered'>
                <thead>
                    <tr className='bg-danger'>
                    <th>Sl No</th>
                    <th>Name Of Material</th>
                    <th>UOM</th>
                    <th>QTY</th>
                    <th>Price</th>
                    <th>Total</th>
                    </tr>
                </thead>
                <tbody>
                   {
                    itemlist.map((info,index)=>{
                        return(
                            <tr className='bg-primary'>
                                <td>{index+1}</td>
                                <td>{info.name}</td>
                                <td>{info.uom}</td>
                                <td>{info.qty}</td>
                            </tr>
                        )
                    })
                   }
                </tbody>
                <tfoot>
                    <tr>
                        <td></td>
                        <td></td>
                        <td></td>
                        <td></td>
                        <td>Grand Total</td>
                        <td>6000</td>
                    </tr>
                </tfoot>
            </table>
            

        </div>
    )
 }
 export default Myitem;
